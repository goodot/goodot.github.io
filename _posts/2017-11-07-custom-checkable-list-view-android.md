---
published: true
---
## Checkable custom ListView in Android

Sometimes in Android Development we need checkable ListView  to choose multiple items and do some action simultanously on them. Let's discuss some application about basketball players, it doesn't matter what about is this app, we just discuss only ListView where is represented list of basketball players. In this situation would be better if we use custom items in our ListView to show complex information about players in a single row, e.g. photo of player, name, height and age.

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

![Checkable List View](https://lh3.googleusercontent.com/46I3EOZ_ZX2rC2VDr7AY2hWSP8wrm5cCqbrPXZpHxZTAkzMNC-TgThulj7P-ch79PfuG3UGy2tGOp_dFgD_ftjHF2Q0r6Ky32omLCivMkFqjNEz9IU74Dl6l_PayPXkMXj9Jhj_gLbk7pBYgZfWXiG1t_yi1p135YBpASLtMSdUJpiekiaCI8FxlkbvA2d5U0lvdndfoh9i11V5DS3z2Huq-Q_Wqf2i0Fy58a8rzYlmxHPS0SG1wL9JoJ8dol6nKSp2SztDLgI3pL-A31D-3P1D3cIDMcgDS3UMEHdbJix2SaSIJsaQ9hTqJzLHHp44H1M97l7Nri2yBAUyL8iTEx5vCYzUazo004w4RtZ2C9Qh3OPKfbqhP7ZKJKdx737fkgmhOPrCPifktrHQsU-0obXZd4sQBesiO2gbES-RFpLURqFTPZoRRJRaXJ5521HV2DMqmOBvynf90tYtTy5ab4WZvzB5DshTaACrHIz99Mb79LeOhk3KeA42ACMnW5-kvzCxiW0c8lLci7RPVEbqWTxeMNvcm-WYW4no9HYObmjy0NpMSurh_7d9OP-uPtPYNiOzeCsYxh1Ogrg9ymlx9k9BP_qf3RkZwYpJX7t8WsQ=w358-h593-no)


 **BasketballPlayerAdapter**
