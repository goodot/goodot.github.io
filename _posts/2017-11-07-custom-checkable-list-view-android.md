---
published: true
---
## Checkable custom ListView in Android development

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
	<ListView xmlns:android="http://schemas.android.com/apk/res/android"
      xmlns:app="http://schemas.android.com/apk/res-auto"
      xmlns:tools="http://schemas.android.com/tools"
      android:layout_width="match_parent"
      android:layout_height="match_parent"
      tools:context="com.listview.checkable.checkable_listview.MainActivity">


      <ListView
          android:layout_width="match_parent"
          android:layout_height="match_parent"
          android:id="@+id/list_view"/>

		</ListView>
