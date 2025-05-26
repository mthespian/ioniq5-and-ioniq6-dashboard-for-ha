# ioniq5 & ioniq 6 cards for Home Assistant

# Custom card layouts with images for home assistant for the ionic 5 and ioniq 6


![logo](https://raw.githubusercontent.com/rchiileea/ioniq5-and-ioniq6-dashboard-for-ha/refs/heads/main/Screenshot%202024-10-23%20093930.png)

First off, let me start by what you 100% need to use this,

Download the following from HACS:
 - Hyundai bluelink integration: Kia Uvo / Hyundai Bluelink
 - Custom brand icons
 - card-mod
 - slider-entity-row
 - button-card

If you're running HAOS, installing and configuring the FTP addon from addons will make the uploads easier.


1.  Upload files from the `fonts` folder into your `www` folder (local) (not the fonts folder but the files within)
    
2.  Upload the appropriate `a` and `b` folders for your vehicle into your  `www` folder (local)
    - For Ioniq 5, upload the `ioniq5a` and `ioniq5b` folders
    - For Ioniq 6, upload the `ioniq6a` and `ioniq6b` folders
    - For Ioniq 5 N, upload the `ioniq5na`  and `ioniq5nb`  folders

2.  Upload the  chargeport  `folder` into your `www` folder (local)

3.  Add the fonts and files you have uploaded from fonts folder to home assistant. To do this within Settings/Dashboards:
    1. Click the 3 dots in the top right and click Resources.
    2. Click [+ ADD RESOURCE]
    3. Enter `/local/loadfonts.js` for the URL
    4. Verify "JavaScript module" is selected
    5. Click [CREATE]
    6. Click [+ ADD RESOURCE]
    7. Enter `/local/fonts.css` for the URL
    8. Verify "Stylesheet" is selected
    9. Click [CREATE]

4.  NEXT OPEN THE file "add to configuration.yaml" you downloaded and open it, change only the text in CAPS and replace with the sensor names asked for that you have in your hyundai/kia integration you just installed. Sensor names are something like: sensor.ioniq5_ev_battery_level
    * If you have a 2024 Ioniq 5, check if your entities have `2024_` before their names.  If so, replace appropriate references that begin `ioniq_5_` to instead begin `2024_ioniq_5_`
    # Double check before continuing once you are sure its right, open your home assistant and go to studio code (or via file browser if you have samba setup) open the configuration.yaml in home assistant and copy and paste the text into your configuration.yaml in home assistant.
    
5.  Go to developer tools, stay on the the yaml tab and scroll down and click on TEMPLATE ENTITIES

6.  Decide if you want both top down and rear view, or just one of the two bottom ones from the photo are the alt versions.

7.  Add the card for the first view you selected
    1. Open one of the `ioniq `xxx` view card.yaml` files in a text editor
    2. Update any required elements
       * Ioniq 5
         1. If you have a 2024 Ioniq 5, check if your entities have `2024_` before their names.  If so, replace appropriate references that begin `ioniq_5_` to instead begin `2024_ioniq_5_`
         2. If you have a left-hand drive vehicle make the following substitutions if using `ioniq 5 top view card.yaml`
            1. Change `ioniq5-top-rhd.png` to `ioniq5-top-lhd.png`
            2. Change `wheel.png` to `wheel--lhd.png`
            3. Change `wheel-on.png` to `wheel-on--lhd.png`
       * Ioniq 6
         1. Replace the entities described in ALL-CAPs with the names from your vehicle
            # If you have the enthusiasm, commit this updated yaml to a github repo and submit a pull request of just the view card yamls with these details included
         2. If you have a left-hand drive vehicle make the following substitutions if using `ioniq 6 top view card.yaml`
            1. Change `ioniq6-top-rhd.png` to `ioniq6-top-lhd.png`
            2. Change `wheel-on.png` to `wheel-on-lhd.png`
       * Ioniq 5 N
         1. If you have a left-hand drive vehicle make the following substitutions if using `ioniq 5n top view card.yaml`
            1. Change `ioniq5-top-rhd.png` to `ioniq5-top-lhd.png`
            2. Change `wheel-on.png` to `wheel-on--lhd.png`
   3. Select all the yaml text in the editor and copy
   4. Add a new card on a dashboard
   5. Choose manual (very bottom)
   6. Delete anything that is in the text field
   7. Paste the markup copied from the yaml file into the text field
   8. Save. Done.
8. Repeat for other views as desired

--------------------------------------------------------------

Sit back enjoy, I'll update the code if I add anymore (or if integration gets buttons added for start and stop charge in the future)

------------------------------------------------------------

Thank you to Nathan Jones from facebook for the alt rear view idea and input and Carton on HA discord for help with the charge port code
