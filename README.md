PagerSlidingTitleIconTabStrip
=============================

You can add an icon next to tab title. Update form https://github.com/astuetz/PagerSlidingTabStrip

compitable with PagerSlidingTabStrip completely!

Example:

public class MainFragmentPagerAdapter extends FragmentPagerAdapter implements TitleIconTabProvider{

	private final int[] TITLES = {R.string.text1_label,R.string.text2_label,R.string.text3_label};
	private final String[] fragments = {
			
			Fragment1.class.getName(),
			Fragment2.class.getName(),
			Fragment3.class.getName()
			};
	private final int[] icons = {TitleIconTabProvider.NONE_ICON,R.drawable.ic_action_video,TitleIconTabProvider.NONE_ICON};
	private Context ctx;

	public MainFragmentPagerAdapter(FragmentManager fm,Context ctx) {
		super(fm);
		this.ctx = ctx;
	}

	@Override
	public CharSequence getPageTitle(int position) {
		return ctx.getString(TITLES[position]);
	}

	@Override
	public int getCount() {
		return TITLES.length;
	}

	@Override
	public Fragment getItem(int position) {

		return Fragment.instantiate(ctx,fragments[position]);

	}

	@Override
	public int getPageIconResId(int position) {
		
		return icons[position];
	}

}
