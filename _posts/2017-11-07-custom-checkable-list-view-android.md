---
published: true
---
## Checkable custom ListView in Android

Sometimes in Android Development we need checkable ListView  to choose multiple items and do some actions simultanously on them. Let's discuss some application about basketball players, it doesn't matter what about is this app, we just talk only about ListView where is represented list of basketball players. In this situation would be better if we use custom items in our ListView to show complex information about players in a single row, e.g. photo of player, name, height and age.

**Player Model**



First of all we create class which describes player:




    public class BasketballPlayer {

        private String name;
        
        private Integer height;
        private int imageResource;
        private Integer age;
        public String getName() {
                return name;
            }
        
            public void setName(String name) {
                this.name = name;
            }
        
            public Integer getHeight() {
                return height;
            }
        
            public void setHeight(Integer height) {
                this.height = height;
            }
        
            public int getImageResource() {
                return imageResource;
            }
        
            public void setImageResource(int imageResource) {
                this.imageResource = imageResource;
            }
        
            public Integer getAge() {
                return age;
            }
        
            public void setAge(Integer age) {
                this.age = age;
            }
    }

**Activity and ListView**

Let's create activity which contains ListView (In this example we have LinearLayout): 
	
    <? xml version="1.0" encoding="utf-8"?>
	<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context="com.listview.checkable.checkable_listview.MainActivity">


    <ListView
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:id="@+id/list_view"/>

	</LinearLayout>
    
 __name of file: activity_main.xml
 
 
 
**Custom checkable layout**

Now we should create java class which will extent RelativeLayout class and implements Checkable interface. Also we can extend different layouts e.g. Linear, Constraint or etc, but in this example we choose Relative.

If we imagine our list view graphically we have view like that, list view with RelativeLayout items; all of them are checkable:

![Checkable List View]({{site.baseurl}}/https://lh3.googleusercontent.com/46I3EOZ_ZX2rC2VDr7AY2hWSP8wrm5cCqbrPXZpHxZTAkzMNC-TgThulj7P-ch79PfuG3UGy2tGOp_dFgD_ftjHF2Q0r6Ky32omLCivMkFqjNEz9IU74Dl6l_PayPXkMXj9Jhj_gLbk7pBYgZfWXiG1t_yi1p135YBpASLtMSdUJpiekiaCI8FxlkbvA2d5U0lvdndfoh9i11V5DS3z2Huq-Q_Wqf2i0Fy58a8rzYlmxHPS0SG1wL9JoJ8dol6nKSp2SztDLgI3pL-A31D-3P1D3cIDMcgDS3UMEHdbJix2SaSIJsaQ9hTqJzLHHp44H1M97l7Nri2yBAUyL8iTEx5vCYzUazo004w4RtZ2C9Qh3OPKfbqhP7ZKJKdx737fkgmhOPrCPifktrHQsU-0obXZd4sQBesiO2gbES-RFpLURqFTPZoRRJRaXJ5521HV2DMqmOBvynf90tYtTy5ab4WZvzB5DshTaACrHIz99Mb79LeOhk3KeA42ACMnW5-kvzCxiW0c8lLci7RPVEbqWTxeMNvcm-WYW4no9HYObmjy0NpMSurh_7d9OP-uPtPYNiOzeCsYxh1Ogrg9ymlx9k9BP_qf3RkZwYpJX7t8WsQ=w358-h593-no)


So implementation of checkable would look like this:

    public class BasketballPlayerAdapter extends BaseAdapter {
        private Context context;
        private ArrayList<BasketballPlayer> basketballPlayers;

        public BasketballPlayerAdapter(Context context, ArrayList<BasketballPlayer> basketballPlayers){
            this.context = context;
            this.basketballPlayers = basketballPlayers;

        }

        @Override
        public int getCount() {
            return this.basketballPlayers.size();
        }

        @Override
        public BasketballPlayer getItem(int position) {
            return this.basketballPlayers.get(position);
        }

        @Override
        public long getItemId(int position) {
            return position;
        }

        @Override
        public View getView(int position, View convertView, ViewGroup parent) {
            LayoutInflater inflater = (LayoutInflater)context.getSystemService(Context.LAYOUT_INFLATER_SERVICE);
            View view = inflater.inflate(R.layout.list_view_item, parent, false);

            ImageView playerPhotoImageView = (ImageView) view.findViewById(R.id.player_photo_image_view);
            TextView playerNameTextView = (TextView) view.findViewById(R.id.player_name_text_view);
            TextView playerAgeTextView = (TextView) view.findViewById(R.id.player_age_text_view);
            TextView playerHeightTextView = (TextView) view.findViewById(R.id.player_height_text_view);

            BasketballPlayer basketballPlayer = this.basketballPlayers.get(position);

            playerPhotoImageView.setImageDrawable(context.getResources().getDrawable(basketballPlayer.getImageResource()));
            playerNameTextView.setText(basketballPlayer.getName());
            String age = basketballPlayer.getAge().toString();
            playerAgeTextView.setText(new StringBuilder(age).append(" years old"));
            String height = basketballPlayer.getHeight().toString();
            playerHeightTextView.setText(new StringBuilder(height).append(" cm"));


            return view;
        }
    }

**ListView item layout**

First of all let's create some selectors which changes it's condition on check. We need text color selector and some image selector, when user checks the item, texts on items should change colors and also would be nice if there were some graphical indicator which represents is item checked or not, for example we use tick icon to represent checked condition.

_check_drawable_selector.xml_

	<?xml version="1.0" encoding="utf-8"?>
      <selector xmlns:android="http://schemas.android.com/apk/res/android">
          <item android:state_checked="true" android:drawable="@drawable/checked" />
      </selector>

_check_color_selector.xml_

    <?xml version="1.0" encoding="utf-8"?>
    <selector xmlns:android="http://schemas.android.com/apk/res/android">
        <item android:state_checked="false" android:color="#6000" />
        <item android:color="#4580ff"/>
    </selector>


and now we use this selectors in our ListView item:

_list_veiw_item.xml_

     <com.listview.checkable.checkable_listview.CheckableRelativeLayout
        xmlns:android="http://schemas.android.com/apk/res/android"
        xmlns:app="http://schemas.android.com/apk/res-auto"
        android:layout_width="match_parent"
        android:layout_height="80dp">


        <ImageView
            android:id="@+id/player_photo_image_view"
            android:layout_width="60dp"
            android:layout_height="80dp"
            android:layout_alignParentStart="true"
            android:layout_alignParentTop="true"
            app:srcCompat="@drawable/ginobili"
            android:layout_marginStart="5dp"/>

        <TextView
            android:id="@+id/player_name_text_view"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:duplicateParentState="true"
            android:layout_alignParentTop="true"
            android:layout_marginStart="21dp"
            android:layout_marginTop="13dp"
            android:textColor="@color/check_color_selector"
            android:layout_toEndOf="@+id/player_photo_image_view"
            android:text="Emanuel Ginobili"
            android:textSize="18sp"
            android:textStyle="bold" />

        <TextView
            android:id="@+id/player_height_text_view"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:duplicateParentState="true"
            android:textColor="@color/check_color_selector"
            android:layout_alignParentBottom="true"
            android:layout_alignStart="@+id/player_name_text_view"
            android:layout_marginBottom="10dp"
            android:text="198 cm" />

        <TextView
            android:id="@+id/player_age_text_view"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:duplicateParentState="true"
            android:textColor="@color/check_color_selector"
            android:layout_alignBaseline="@+id/player_height_text_view"
            android:layout_alignBottom="@+id/player_height_text_view"
            android:layout_centerHorizontal="true"
            android:text="40 years old" />

        <ImageView
            android:id="@+id/imageView2"
            android:layout_width="40dp"
            android:layout_height="40dp"
            android:layout_alignParentEnd="true"
            android:layout_centerVertical="true"
            android:duplicateParentState="true"
            android:layout_marginEnd="24dp"
            app:srcCompat="@drawable/check_drawable_selector" />
    </com.listview.checkable.checkable_listview.CheckableRelativeLayout>
    

![list_view_item.xml](https://lh3.googleusercontent.com/YmycOtoZKepin7MpKo2eZyNznQ33yzlMQplGluqvupvBxDYo_AvvnifZenmz1D4g8AEptCaJ0zZ4JpZj-qP3mufqFvmIpSOBkyteuqWeW1zjWpP-STW8Ckzs6wLaDX0A-y8BfI0WWOdhAoPgQ2VthvqzQeCaSw1xDtfAowXEWAwh6hek02Qq_VdJWk5_s2uGOZeAs2qJj_37iyB_N5iN6r3IluvxhUakcE2iofBSCqf10GBEJxgogYUFmqmltVYUOBeu6-ZUhsczAWrJ79-6zB5H9zFArs3rYHamWBf_9b51gHYWWddZoy52DwconzVkspDKAk0oExSgvjN74bE6vS1zHPZtqJjyrNsCIw5jTaotURlwQc5RrpUQmmshkjnfwbiMgnf1TlhqN_Rc7q4lWSySWjXWPqL1netlnwXndsrxEA6MG04-x_oabrofSYwJT0uENI6KJ9rMoUqxoLok-r967QId8a2QU5fnMm8cux-cXs8dxGi_wwnWhorInIkag6Fy2KfRmM9TyndNQFRs-J-OMvppIquNbTwZxg98stjCi_G5YkO17dwB_3U-wduLHBzkZ9ZHMMmMmwntO3BlqaRLEk3YTYEV3AlitOnIHA=w383-h81-no)


 **BasketballPlayerAdapter**
 
 To use our custom item and layout in list view we should make custom adapter to unite them. Let's create java class which extends BaseAdapter:



    public class BasketballPlayerAdapter extends BaseAdapter {
        private Context context;
        private ArrayList<BasketballPlayer> basketballPlayers;

        public BasketballPlayerAdapter(Context context, ArrayList<BasketballPlayer> basketballPlayers){
            this.context = context;
            this.basketballPlayers = basketballPlayers;

        }

        @Override
        public int getCount() {
            return this.basketballPlayers.size();
        }

        @Override
        public BasketballPlayer getItem(int position) {
            return this.basketballPlayers.get(position);
        }

        @Override
        public long getItemId(int position) {
            return position;
        }

        @Override
        public View getView(int position, View convertView, ViewGroup parent) {
            LayoutInflater inflater = (LayoutInflater)context.getSystemService(Context.LAYOUT_INFLATER_SERVICE);
            View view = inflater.inflate(R.layout.list_view_item, parent, false);

            ImageView playerPhotoImageView = (ImageView) view.findViewById(R.id.player_photo_image_view);
            TextView playerNameTextView = (TextView) view.findViewById(R.id.player_name_text_view);
            TextView playerAgeTextView = (TextView) view.findViewById(R.id.player_age_text_view);
            TextView playerHeightTextView = (TextView) view.findViewById(R.id.player_height_text_view);

            BasketballPlayer basketballPlayer = this.basketballPlayers.get(position);

            playerPhotoImageView.setImageDrawable(context.getResources().getDrawable(basketballPlayer.getImageResource()));
            playerNameTextView.setText(basketballPlayer.getName());
            playerAgeTextView.setText(basketballPlayer.getAge().toString() + " years old");
            playerHeightTextView.setText(basketballPlayer.getHeight().toString() + " cm");


            return view;
        }
    }


**Using Custom Adapter**

Now its time to use our custom adapter in the activity where list view is initialized, whole main activity class looks like that:

_MainActivity.java_


      public class MainActivity extends AppCompatActivity {
          ListView listView;


          @Override
          protected void onCreate(Bundle savedInstanceState) {
              super.onCreate(savedInstanceState);
              setContentView(R.layout.activity_main);



              listView = (ListView) findViewById(R.id.list_view);

              final ArrayList<BasketballPlayer> basketballPlayers = new ArrayList<>();

              BasketballPlayer player1 = new BasketballPlayer();
              player1.setImageResource(R.drawable.ginobili);
              player1.setName("Emanuel Ginobili");
              player1.setAge(40);
              player1.setHeight(198);

              BasketballPlayer player2 = new BasketballPlayer();
              player2.setImageResource(R.drawable.rodriguez);
              player2.setName("Sergio Rodriguez");
              player2.setAge(31);
              player2.setHeight(191);

              BasketballPlayer player3 = new BasketballPlayer();
              player3.setImageResource(R.drawable.zaza);
              player3.setName("Zaza Pachulia");
              player3.setAge(33);
              player3.setHeight(211);

              BasketballPlayer player4 = new BasketballPlayer();
              player4.setImageResource(R.drawable.boris);
              player4.setName("Boris Diaw");
              player4.setAge(35);
              player4.setHeight(203);

              basketballPlayers.add(player1);
              basketballPlayers.add(player2);
              basketballPlayers.add(player3);
              basketballPlayers.add(player4);

              BasketballPlayerAdapter adapter = new BasketballPlayerAdapter(this, basketballPlayers);

              listView.setAdapter(adapter);
              listView.setChoiceMode(AbsListView.CHOICE_MODE_MULTIPLE);
              

              
          }
      }
      
lets look at our main activity and pass it step by step. Here we have some ArrayList of BasketballPlayer objects to collect all checked basketball players from list view. 

		selectedPlayers = new ArrayList<>();

Then we fill ArrayList of basketball players for list view and create BasketballPlayerAdapter object using it:



      				final ArrayList<BasketballPlayer> basketballPlayers = new ArrayList<>();

                    BasketballPlayer player1 = new BasketballPlayer();
                    player1.setImageResource(R.drawable.ginobili);
                    player1.setName("Emanuel Ginobili");
                    player1.setAge(40);
                    player1.setHeight(198);

                    BasketballPlayer player2 = new BasketballPlayer();
                    player2.setImageResource(R.drawable.rodriguez);
                    player2.setName("Sergio Rodriguez");
                    player2.setAge(31);
                    player2.setHeight(191);

                    BasketballPlayer player3 = new BasketballPlayer();
                    player3.setImageResource(R.drawable.zaza);
                    player3.setName("Zaza Pachulia");
                    player3.setAge(33);
                    player3.setHeight(211);

                    BasketballPlayer player4 = new BasketballPlayer();
                    player4.setImageResource(R.drawable.boris);
                    player4.setName("Boris Diaw");
                    player4.setAge(35);
                    player4.setHeight(203);

                    basketballPlayers.add(player1);
                    basketballPlayers.add(player2);
                    basketballPlayers.add(player3);
                    basketballPlayers.add(player4);

                    BasketballPlayerAdapter adapter = new BasketballPlayerAdapter(this, basketballPlayers);
                

Set adapter to list view and also set choice mode:


			listView.setAdapter(adapter);
            listView.setChoiceMode(AbsListView.CHOICE_MODE_MULTIPLE);
      

Finally our list view looks like : 

![](https://lh3.googleusercontent.com/tLxpoMPOqaNkLHVWwau_MNwWR1TEir0z-25jDW-9SXyChfaxgepKBv4BYtSCA3lpxfuMiaAnMGFdLxOQ5yGgg29AhIbywxlP2BypP7_x2O78AVk_Ok-EYAoM4oolOe3FuJUWxDx6gak5Cf_wk8hykEtj2FLB1Bn01jQzZF_OiFrTldl3ov9gQ6WbzpIz22k3OkSVG6isNs2WF2drhMtPIV7jmbm5nx_hMQTrNWibGlKuU4WQxqSJMfMTYaDeqpQR8B-nttTfD_fGzDkfNTJls7HgcUOBcU_mprtmi2gSBMC3_sU8zunrfhgy1j6VyQG3j4WX5LnC-UUdIEC1khGLv67EqJQYB_hO_UrDxe8ljzvCOFIQtk4zJkrXkyHTNYYqUdO-cWIHaRWwDZqlSRbVkf-7shnyqp86YeWKVqJBxqyJD08jHM0uLcIBgFWActLjxX23hWBfRTh756NByYuQqdoUGqedhxQn8rbRWh1tk-mxR4fR2Zpjws2P7OfSJf9SXuwN69BSaJF_LQOsS3dBVVmearnwKUpBFfFv9wsqng-nUxhLth8w-ydNDZQ4kMxspX5Qh6QSpLDL8m9II3F6GpbF7rW5uSWPn0sRrfXPAg=w525-h933-no)





_Clone source: [https://github.com/goodot/custom-checkable-list-view](https://github.com/goodot/custom-checkable-list-view)_





