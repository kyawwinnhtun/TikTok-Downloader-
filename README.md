**TikTok-Downloader**

**Library**

```
com.github.Thawtarlamin:TikTok-Downloader:1.3.0
```
**Permission**

```
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>
    <uses-permission android:name="android.permission.ACCESS_WIFI_STATE"/>
    <uses-permission android:name="android.permission.INTERNET"/>
```

**ImageView AsyncTask**

```
class DownloadImageTask extends AsyncTask<String, Void, Bitmap> {

    ImageView bmImage;



    public DownloadImageTask(ImageView bmImage) {

        this.bmImage = bmImage;

    }



    protected Bitmap doInBackground(String... urls) {

        String urldisplay = urls[0];

        Bitmap mIcon11 = null;

        try {

            InputStream in = new java.net.URL(urldisplay).openStream();

            mIcon11 = BitmapFactory.decodeStream(in);

        } catch (Exception e) {

            Log.e("Error", e.getMessage());

            e.printStackTrace();

        }

        return mIcon11;

    }



    protected void onPostExecute(Bitmap result) {

        bmImage.setImageBitmap(result);

    }

}
```

**Download Manager**

```
String url = "url you want to download";

DownloadManager.Request request = new DownloadManager.Request(Uri.parse(url));

request.setDescription("Some descrition");

request.setTitle("Some title");

// in order for this if to run, you must use the android 3.2 to compile your app

if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.HONEYCOMB) {

    request.allowScanningByMediaScanner();

    request.setNotificationVisibility(DownloadManager.Request.VISIBILITY_VISIBLE_NOTIFY_COMPLETED);

}

request.setDestinationInExternalPublicDir(Environment.DIRECTORY_DOWNLOADS, "name-of-the-file.ext");



// get download service and enqueue file

DownloadManager manager = (DownloadManager) getSystemService(Context.DOWNLOAD_SERVICE);

manager.enqueue(request);
```

**Donate PayPal**
```
nyeineikhin.nek@gmail.com
```
**Tanks for all my friends**





