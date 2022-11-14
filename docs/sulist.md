## SuList

  - MagiskHide in whitelist mode, only process on sulist will able to obtain root access, Magisk keeps invisible for other processes
  - SuList has the strongest root hiding ability because of limited modification of the application environment
  - SuList uses logcat to monitor application startup, please do not disable logcat service or you will lose root.
  - SuList uses separate lists.  After enabling SuList and restarting, you should be able to configure sulist
  - Select apps that need Magisk access to SuList, not banking apps. Apps on sulist are immediately mounted su when launcing and will also be granted root access from Magisk.
  - SuList requires MagiskHide to be enabled but works a little different from MagiskHide
  - SuList applies unmount Magisk directly in zygote, zygote will no longer read the module file after it finishes booting.
  - SuList cannot coexist with Zygisk. Modules functionality are less compatible. Most modules will not work or broken in SuList because of the way it works.  Please don't ask why some modules don't work or system crashes.
  - SuList cannot be enabled and disabled immediately without restarting
