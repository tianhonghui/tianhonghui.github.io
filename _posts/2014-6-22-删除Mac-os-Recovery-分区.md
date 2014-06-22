Deleting and merging a partition with diskutil from the command line
This is the most precise method I know of to remove the partition since it targets the recovery disk directly and merges it with the full Lion partition – if you’re not comfortable with the command line this is not for you.

- Launch the Terminal and type the following into the command line:

{% highlight js%}
diskutil list
{% endhighlight %}

This will print out your drives partition scheme and look something like this:

diskutil list

- Look for “Recovery HD” and see which identifier it is using, it this screenshot it’s disk0s4
To remove that partition we use the following command (you can also use the volume name):

{% highlight js%}
diskutil eraseVolume HFS+ Blank /dev/disk0s4
{% endhighlight %}

- The partition will be erased, you might want to do this with your standard Lion partition as well since you’ll be wiping the entire thing anyway. Regardless, you’ll now have a blank partition sitting around, so you’ll want to merge that with your other Lion partition:

{% highlight js%}
diskutil mergePartitions HFS+ Lion disk0s3 disk0s4
{% endhighlight %}
	
- This will merge the two partitions, with disk0s3 absorbing the space from disk0s4 and expanding, it causes data loss so don’t expect this to preserve anything
The next approach is much more invasive because it formats the entire disk.