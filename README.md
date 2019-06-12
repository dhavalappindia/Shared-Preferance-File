package utils;

import android.annotation.TargetApi;
import android.content.Context;
import android.content.SharedPreferences;
import android.os.Build;

@TargetApi(Build.VERSION_CODES.HONEYCOMB)
public class MyPreference {
    SharedPreferences myPrefs;
    SharedPreferences.Editor prefEditor;
    Context context;

   


    @SuppressWarnings("static-access")
    public MyPreference(Context context) {
        this.context = context;
        myPrefs = context.getSharedPreferences("bank_detailes", context.MODE_PRIVATE);
    }

    public void clearPrefs() {
        prefEditor = myPrefs.edit();
        prefEditor.clear();
        prefEditor.commit();
    }

    public void setOfferWallDataResponse(String res) {
        prefEditor = myPrefs.edit();
        prefEditor.putString("moreapps", res);
        prefEditor.commit();
    }

    public String getOfferWallDataResponse() {
        return myPrefs.getString("moreapps", "");
    }

    /*----------------------------------------user points-----------------------------------------*/
    public void setUserPoints(String userPoints) {
        prefEditor = myPrefs.edit();
        prefEditor.putString("userPoints", userPoints);
        prefEditor.commit();

    }

    public String getUserPoints() {
        return myPrefs.getString("userPoints", "");
    }


    /*----------------------------------------user Referral points-----------------------------------------*/
    public void setUserReferralPoints(int userPoints) {
        prefEditor = myPrefs.edit();
        prefEditor.putInt("referral_points", userPoints);
        prefEditor.commit();

    }

    public int getUserReferralPoints() {
        return myPrefs.getInt("referral_points", 0);
    }

  
    /*----------------------------------------user email-----------------------------------------*/

    public void setUserEmail(String userEmail) {
        prefEditor = myPrefs.edit();
        prefEditor.putString("userEmail", userEmail);
        prefEditor.commit();

    }

    public String getuserEmail() {
        return myPrefs.getString("userEmail", "");
    }

    /*----------------------------------------user profile url-----------------------------------------*/

    public void setUserProfilUrl(String userProfilUrl) {
        prefEditor = myPrefs.edit();
        prefEditor.putString("userProfilUrl", userProfilUrl);
        prefEditor.commit();

    }

    public String getuserProfilUrl() {
        return myPrefs.getString("userProfilUrl", "");
    }
    
    
    
    
    

    /*-----------------------------Boolean data-------------------------------------------*/
    /*----------------------------------------user is login-----------------------------------------*/


    public void setIsLogin(boolean isLogin) {
        prefEditor = myPrefs.edit();
        prefEditor.putBoolean("isLogin", isLogin);
        prefEditor.commit();
    }

    public boolean getIsLogin() {
        return myPrefs.getBoolean("isLogin", false);
    }


    /*-----------------------------is Rated App-------------------------------------------*/
    public void setISRatedApp(boolean isRatedApp) {
        prefEditor = myPrefs.edit();
        prefEditor.putBoolean("isRatedApp", isRatedApp);
        prefEditor.commit();
    }

    public boolean getISRatedApp() {
        return myPrefs.getBoolean("isRatedApp", true);
    }
    /*-----------------------------------------------------------------------------------*/








   /*-----------------------------String data-------------------------------------------*/
   /*-----------------------------------------------------------------------------------*/
    // ---------------------------- common one or more value-----------------------------------------

    public void setData(String key, String value) {
        prefEditor = myPrefs.edit();
        prefEditor.putString("key" + key, value);
        prefEditor.commit();
    }

    public String getData(String key) {
        return myPrefs.getString("key" + key, "");
    }
    
    /*-----------------------------------------------------------------------------------*/
}
