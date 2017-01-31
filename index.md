# Repositories

<a href="https://github.com/worknrole/android-design" class="content_link" target="_blank">android-design</a>: Contains some user interfaces implementation. Trying to improve my knowledge about Android UI conception (MaterialDesign advice, support libraries, custom views, custom styles, resources ...).

<a href="https://github.com/worknrole/android-sample" class="content_link" target="_blank">android-sample</a>: Contains samples about android SDK and external libraries.  


# Reminder

**&#126; Butter Knife -** Something like:

{% highlight java %}
public class MainActivity extends AppCompatActivity {
	@BindView(R.id.myBtnId) private Button mBtn;

	@Override
	protected void onCreate(Bundle savedInstanceState) {
		...
    	    ButterKnife.bind(this);
	}

	@OnClick(R.id.myBtnId)
	public void myBtnClickMethod() {
		// Manage the onClick event
	}
{% endhighlight %}


**&#126; Retrofit 2.0 -** Something like:

{% highlight java %}
// Create the service
public interface MyService() {
	@GET(search/{kitty})
	Call<Kitty> searchKitty(@Path("name") String kittyName)
}
{% endhighlight %}

{% highlight java %}
// Make a callable service
MyService service = new Retrofit.Builder()
	.baseUrl(MY_API_URL)
	.addConvertorFactory(GsonConverterFactory.create())
	.build()
	.create(MyService.class);
}
{% endhighlight %}

{% highlight java %}
// Call and retrieve the service response
Call<Kitty> call = service.searchKitty("Noisette");
call.enqueue(new Callback<Kitty>() { ... }
{% endhighlight %}