![Cover]()
OK, kita berjumpa lagi di tutorial kedua dalam membuat aplikasi *Foodbank*. Semoga kita semua tetap di istiqomahkan dalam belajar dan diberi kemudahan dalam menerima ilmu-ilmunya Allah. Aamiinn....

Kali ini kita akan membuat *WelcomeScreen* dapat berfungsi sebagaimana mestinya. Langkah-langkahnya antara lain :

1. Buka Project yang sudah kita buat di pertemuan sebelumya, kalau teman - teman baru mengikuti di pertemuan ini, silahkan buka dulu ya tutorial pada part 1 [disini](https://congfandi.github.io/2019/03/26/membuat-aplikasi-foodbank-part-1/).
   
2. Buka file *`activity_welcome.xml`* yang ada pada folder(*package*) `res/layout` .
   
3. Kemudian gantilah `CODE` nya dengan code dibawh ini
   ```xml
        <?xml version="1.0" encoding="utf-8"?>
        <RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
            xmlns:app="http://schemas.android.com/apk/res-auto"
            xmlns:tools="http://schemas.android.com/tools"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            tools:context=".views.WelcomeActivity">
            <android.support.v4.view.ViewPager
                android:id="@+id/viewpager"
                android:layout_width="match_parent"
                android:layout_height="match_parent"/>
        </RelativeLayout>
   ```

4. Buatlah tiga file yang ada pada direktori (*package*) `res/layout` 
   - [ ] `welcome_first.xml`  
   - [ ] `welcome_second.xml`  
   - [ ] `welcome_third.xml`
  
    Lihatlah gambar 1.
    ![Gambar 1](/../img/05-04-2019/gambar1.png)
    *Gambar 1*

5. Edit dan tambahkan tiga file diatas dengan kode seperti dibawah ini :
    - `welcome_first.xml`
    ```xml
        <?xml version="1.0" encoding="utf-8"?>
        <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
            android:layout_width="match_parent"
            android:layout_height="match_parent">
            <TextView
                android:text="First"
                android:layout_width="match_parent"
                android:layout_height="match_parent" />
        </LinearLayout>
    ```

    - `welcome_second.xml`
    ```xml
        <?xml version="1.0" encoding="utf-8"?>
        <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
            android:layout_width="match_parent"
            android:layout_height="match_parent">
            <TextView
                android:text="Second"
                android:layout_width="match_parent"
                android:layout_height="match_parent" />
        </LinearLayout>
    ```

    - `welcome_third.xml`
    ```xml
        <?xml version="1.0" encoding="utf-8"?>
        <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
            android:layout_width="match_parent"
            android:layout_height="match_parent">
            <TextView
                android:text="Third"
                android:layout_width="match_parent"
                android:layout_height="match_parent" />
        </LinearLayout>
    ```

6. Edit file `string.xml` yang ada pada direktori `res/values` kemudian tambahkan code dibawah ini
   ```xml
        <string name="_first">First</string>
        <string name="_second">Second</string>
        <string name="_third">Third</string>
   ```

7. Buatlah File **ENUM** pada direktori(*package*) *`id.gresikdev.foodbank => models`* dengan nama file **`WelcomeModel.java`**
   
8. Isi file yang teman-teman buat dengan code dibawah ini
   
   ```java
        package id.gresikdev.foodbank.models;

        import id.gresikdev.foodbank.R;

        public enum WelcomeModel {
            FIRSTVIEW(R.string._first, R.layout.welcome_first),
            SECONDVIEW(R.string._second, R.layout.welcome_second),
            THIRDVIEW(R.string._third, R.layout.welcome_third);

            private int mTitleResId;
            private int mLayoutResId;

            WelcomeModel(int titleResId, int layoutResId) {
                mTitleResId = titleResId;
                mLayoutResId = layoutResId;
            }

            public int getTitleResId() {
                return mTitleResId;
            }

            public int getLayoutResId() {
                return mLayoutResId;
            }

        }
   ```

9. Buatlah Package dengan nama `adapter` kemudian buatlah sebuah file di dalamnya dengan nama `WelcomeAdapter.java` . lihatlah pada gambar 2.
    ![Gambar 2](/../img/05-04-2019/gambar2.png)

10. Buka file `WelcomeAdapter.java` kemudian tambahkan code berikut
    
    ```java
            package id.gresikdev.foodbank.adapter;

            import android.content.Context;
            import android.support.annotation.NonNull;
            import android.support.annotation.Nullable;
            import android.support.v4.view.PagerAdapter;
            import android.view.LayoutInflater;
            import android.view.View;
            import android.view.ViewGroup;

            import id.gresikdev.foodbank.models.WelcomeModel;

            public class WelcomeAdapter extends PagerAdapter {
                private Context mContext;

                public WelcomeAdapter(Context context) {
                    mContext = context;
                }

                @NonNull
                @Override
                public Object instantiateItem(@NonNull ViewGroup container, int position) {
                    WelcomeModel welcomeModel = WelcomeModel.values()[position];
                    LayoutInflater inflater = LayoutInflater.from(mContext);
                    ViewGroup layout = (ViewGroup) inflater.inflate(welcomeModel.getLayoutResId(),container,false);
                    container.addView(layout);
                    return layout;
                }

                @Override
                public void destroyItem(@NonNull ViewGroup container, int position, @NonNull Object object) {
                    container.removeView((View)object);
                }

                @Override
                public int getCount() {
                    return WelcomeModel.values().length;
                }

                @Override
                public boolean isViewFromObject(@NonNull View view, @NonNull Object o) {
                    return view == o;
                }

                @Nullable
                @Override
                public CharSequence getPageTitle(int position) {
                    WelcomeModel welcomeModel = WelcomeModel.values()[position];
                    return  mContext.getString(welcomeModel.getTitleResId());
                }
            }
    ````

11. Buka File `WelcomeActivity.java` kemudian edit dan tambahkan code dibawah ini 
        
    ```java
            package id.gresikdev.foodbank.views;

            import android.support.v4.view.ViewPager;
            import android.support.v7.app.AppCompatActivity;
            import android.os.Bundle;

            import id.gresikdev.foodbank.R;
            import id.gresikdev.foodbank.adapter.WelcomeAdapter;

            public class WelcomeActivity extends AppCompatActivity {

                private  ViewPager viewPager;

            private void setViewPager(){
                    viewPager = findViewById(R.id.viewpager);
                    viewPager.setAdapter(new WelcomeAdapter(this));
                }

                @Override
                protected void onCreate(Bundle savedInstanceState) {
                    super.onCreate(savedInstanceState);
                    setContentView(R.layout.activity_welcome);
                    setViewPager();
                }
            }
    ```
12. Jalankan aplikasi dan kalian sudah selesai membuat `logic` nya. terlihat tampilan seperti dibawah ini 