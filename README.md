# Moving-ticker
What is TickerView?
TickerView is a simple UI component for displaying horizontally scrolling Views placed inside this TickerView. For reference you may see how MoneyControl Tablet (shows stock price in scrolling view at the bottom of screen) and Phone app shows the Stock prices. The TickerView scrolls child views with smooth animation.

How it Works?
TickerView extends HorizontalScrollView, which contains a LinearLayout. With the method setChildViews(List childViews)" or "addChildView(View childView)", we add child views to be plotted in the scrolling TickerView. Once Views are added to the TickerView, we set the left Margin for the First View and the right Margin for the Last View equalent to the width of the screen, so that the view statys on the screen for a certain time frame. Additionally, we have added a Marker View as the last view on the list, so that as soon as that view's Rect bounds (with width and height equal to the width and height of parent) intersects with the Rect object of the last Marker View. As soon as this contition is met, we reset the position of scroll and the auto scrolling starts back from the first View.

Now to Automate the Scrolling process, we have created a Timer (which runs TimerTask) which schedule the movement/displacement given by the getDisplacement() method and the process continues till the view is detatched from windlow.
