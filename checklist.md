## Tasks ##
Following tasks are identified:

* create picture set that represents one test (pack it along with json file into a zip file) and place it on public available URL
* API that responds with json (array of TestInfo objects) - mock, firebase...
* Fetch Test list from that API.
* Create Activity/Fragment with a list of available tests to download (when downloaded populate list, on element click start download service)
* Download Service (create folder named <TestID>, unzip pictures and plates.json there, run Local Database Service to add TestInfo to local tests)
* Create Activity/Fragment with a list of downloaded (local) tests (run Local Database Service to populate list, on element click start run test activity)
* Create RunTest Activity (that should run chosen test, need to be implemented as a package for ech test type to ensure that questions and input from users fit the test eg. integer input for Ishihara test, click on rectangle that has different colour for another test etc)
* PlateFragments that are designe for a concrete test type
* Create logic to summerize test results
* Create payload of ResultSet an upload/POST as json to results server (store in local storage/database to summerize results from more then one test)
