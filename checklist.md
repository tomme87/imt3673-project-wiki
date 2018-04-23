## Tasks ##
Following tasks are identified:
Main goal is an app that can run standard tests, like Basic Ishihara, that has some variance in plates and randomized sequence of plates. Use plates with numbers and input as free text not buttons that suggest an answer.
Could support wider range of colors than sRGB (then bound to minimum Android 8.0, API 26+)

* create picture set that represents one test (pack it along with json file into a zip file) and place it on public available URL, (different sets of pictures ?)
* (optional) create one set of .svg files and randomize colours on local device
* API that responds with json (array of TestInfo objects) - mock, firebase, mLab+GO... (data need to match resources URL)
* Fetch Test list from that API (optional list of tests as a json file on given url).
* Create Activity/Fragment with a list of available tests to download (when downloaded populate list, on element click start download service)
* Local database (stores Test Info for downloaded and available - decide when to update list from a server - is it needed evry time the list is shown?)
* Download Service (create folder named <TestID>, unzip pictures and plates.json there, run Local Database Service to add TestInfo to local tests)
* (optional) Create folder named <TestID> with pictures and plates.json in Assets. Use the for GUI/Run Test Activity as a demo/default. Replace with internal storage later (or keep both sources?)
* Create Activity/Fragment with a list of downloaded (local) tests (run Local Database Service to populate list, on element click start run test activity)
* (optional) add mobile screen colour calibration (Enhancing Graphics with Wide Color Content ?)
* (optional) implement Activity to adjust screen brightness before test (do it only once ? onCreate? onResume?)
* Create RunTest Activity (that should run chosen test, need to be implemented as a package for ech test type to ensure that questions and input from users fit the test eg. integer input for Ishihara test, click on rectangle that has different colour for another test etc). All necessary data (pictures from local storage) will be get after "Run test" button clicked (don't fetch resources in advance).
* (optional) Show the same plate multiply times, use eg Plate.priority or randomize (implementation proposal Plate object in Test.plates more than once, but show always then the same number of plates - fixed 15 ?)
* Create JSON parser that could create Set<Plate> out of plates.json file in test folder
* PlateFragments that are designed for a concrete test type (consider timer - eg max 3 sec to give an answer on Ishihara test)
* Create logic to summerize test results
* Create payload of ResultSet an upload/POST as json to results server (store [? security] in local storage/database to summerize results from more then one test)
* (optional) Tests metadata not that important, but eg as a part of metadata use reading from sensors (light enviroment)
