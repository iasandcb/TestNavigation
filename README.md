# TestNavigation

This project demonstrates a fundamental navigation system based on fragments.
In addition to shorcuts of the left menu, it supports a push-pop style flow.

Android Studio 2.1 is used and the minimum SDK of the project is 19 (Android 4.4).

## How to add a top level fragment

Add a new fragment.

Let MainActivity implement OnFragmentInteractionListener of the fragment.

Add a menu item to activity_main_drawer.xml.

Add if statement for the menu item.

    if (id == R.id.nav_new) {
      FragmentTransaction ft = getSupportFragmentManager().beginTransaction();
      ft.replace(R.id.content_frame, new NewFragment());
      ft.commit();
    }

## How to add a sub fragment

Add a new fragment.

Let MainActivity implement OnFragmentInteractionListener of the fragment.

Add a "push" logic to a super fragment.

    getFragmentManager().beginTransaction()
            .add(R.id.content_frame, new NewFragment(), "new")
            .addToBackStack(null)
            .commit();


## Additional Features

### Circular Progress

Tap FAB at right bottom, and you will see a circular progress view. Please refer to MainActivity for more details.

## Note

A sub fragment must have an opaque background, otherwise it shows on its super fragment, and they seem overlapped.
