# testingbranches

class BottomNavbar extends StatefulWidget {
  const BottomNavbar({super.key});

  @override
  State<BottomNavbar> createState() => _BottomNavbarState();
}

class _BottomNavbarState extends State<BottomNavbar> {
  PersistentTabController controller = PersistentTabController();
  List<Widget> _buildScreen() {
    return [
    
 
    
      const HomeScreen(),
      const WalletScreen(),
      const KeyScreen(),
      const ServicesScreen(),
      const AccountScreen()
    ];
  }

  List<PersistentBottomNavBarItem> navbarItems() {
    return [
      //home
      PersistentBottomNavBarItem(
        title: "HOME",
        icon: SvgPicture.asset(
          homeIcon,
          color: appColor,
          height: 24.h,
          width: 22.8.w,
        ),
        activeColorSecondary: appColor,
        activeColorPrimary: appColor,
        inactiveIcon: SvgPicture.asset(
          homeIcon,
          height: 24.h,
          width: 22.8.w,
        ),
        inactiveColorSecondary: appColor,
        opacity: 0.0,
      ),
      //wallet
      PersistentBottomNavBarItem(
        title: "Wallet",
        icon: SvgPicture.asset(
          walletIcon,
          color: appColor,
          height: 24.h,
          width: 22.8.w,
        ),
        activeColorSecondary: appColor,
        activeColorPrimary: appColor,
        inactiveIcon: SvgPicture.asset(
          walletIcon,
          height: 24.h,
          width: 22.8.w,
        ),
        inactiveColorSecondary: appColor,
        opacity: 0.0,
      ),
      //key
      PersistentBottomNavBarItem(
          title: " ",
          icon: SvgPicture.asset(
            keyIcon,
            color: appColor,
            height: 24.h,
            width: 22.8.w,
          ),
          activeColorSecondary: appColor,
          activeColorPrimary: appColor,
          inactiveIcon: SvgPicture.asset(
            keyIcon,
            height: 24.h,
            width: 22.8.w,
          ),
          inactiveColorSecondary: appColor,
          opacity: 0.0),
      //services
      PersistentBottomNavBarItem(
          title: "Service",
          icon: SvgPicture.asset(
            serviceIcon,
            color: appColor,
            height: 24.h,
          ),
          activeColorSecondary: appColor,
          activeColorPrimary: appColor,
          inactiveIcon: SvgPicture.asset(
            serviceIcon,
            height: 24.h,
          ),
          inactiveColorSecondary: appColor,
          opacity: 0.0),
      //Accounat
      PersistentBottomNavBarItem(
          title: "Account",
          icon: SvgPicture.asset(
            accountsIcon,
            height: 24.h,
            width: 22.8.w,
            color: appColor,
          ),
          activeColorSecondary: appColor,
          activeColorPrimary: appColor,
          inactiveIcon: SvgPicture.asset(
            accountsIcon,
            height: 24.h,
            width: 22.8.w,
          ),
          inactiveColorSecondary: appColor,
          opacity: 0.0),
    ];
  }

  @override
  Widget build(BuildContext context) {
    // double h = MediaQuery.of(context).size.height;
    // double w = MediaQuery.of(context).size.width;
    return PersistentTabView(
      context,
      controller: controller,
      screens: _buildScreen(),
      items: navbarItems(),
      confineInSafeArea: true,
      backgroundColor: Colors.white, // Default is Colors.white.
      handleAndroidBackButtonPress: true, // Default is true.
      resizeToAvoidBottomInset:
          true, // This needs to be true if you want to move up the screen when keyboard appears. Default is true.
      stateManagement: true, // Default is true.
      hideNavigationBarWhenKeyboardShows:
          true, // Recommended to set 'resizeToAvoidBottomInset' as true while using this argument. Default is true.
      decoration: NavBarDecoration(
        borderRadius: BorderRadius.circular(10.0.w),
        colorBehindNavBar: Colors.black,
      ),
      popAllScreensOnTapOfSelectedTab: true,
      popActionScreens: PopActionScreensType.all,
      itemAnimationProperties: const ItemAnimationProperties(
        // Navigation Bar's items animation properties.
        duration: Duration(milliseconds: 200),
        curve: Curves.ease,
      ),
      screenTransitionAnimation: const ScreenTransitionAnimation(
        // Screen transition animation on change of selected tab.
        animateTabTransition: true,
        curve: Curves.ease,
        duration: Duration(milliseconds: 200),
      ),
      navBarStyle:
          NavBarStyle.style3, // Choose the nav bar style with this property.
      navBarHeight: 83.h,
    );
  }
}





A new Flutter project.

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Lab: Write your first Flutter app](https://docs.flutter.dev/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://docs.flutter.dev/cookbook)

For help getting started with Flutter development, view the
[online documentation](https://docs.flutter.dev/), which offers tutorials,
samples, guidance on mobile development, and a full API reference.
