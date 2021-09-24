# Release Notes

## Release Summary

IFIX 1.0 is a release that has got a new module, a few functional changes, and non-functional changes.

* Functional: mGramSeva application and Reference Dashboard.
* Non-functional: IFIX Core \(Domain Services\) and IFIX Adaptor.

## New ‌Feature Additions

<table>
  <thead>
    <tr>
      <th style="text-align:left"><a href="http://s.no/"><b>S.No</b></a><b>.</b>
      </th>
      <th style="text-align:left"><b>Feature</b>
      </th>
      <th style="text-align:left"><b>Description</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">1</td>
      <td style="text-align:left">mGramSeva</td>
      <td style="text-align:left">
        <ol>
          <li>Employee Login and User Profile (Forgot, Update/Reset, and Change Password,
            Update Profile).</li>
          <li>Tenant Selection</li>
          <li>Household information (New/Edit/Search Connection)</li>
          <li>Generate Bulk Demand</li>
          <li>Billing (Metered and Non-Metered)</li>
          <li>Revenue - Collect Payment and Generate Receipt</li>
          <li>Expenditure - Add, Search and Update Expense</li>
          <li>Dashboard - Collection and Expense Dashboard (Tabular)</li>
          <li>Post Payment Feedback</li>
          <li>SMS Notifications</li>
          <li>App Onboarding/Walkthrough</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">2</td>
      <td style="text-align:left">Reference Dashboard</td>
      <td style="text-align:left">
        <p>Visualisations/ Metrics on Dashboard</p>
        <ol>
          <li>Surplus/Deficit</li>
          <li>Pending Collections</li>
          <li>Outstanding Electricity Bills</li>
          <li>GPWSCs at Risk</li>
          <li>Collections &amp; Expenditure time series graphs</li>
          <li>Expenditure by Chart of Accounts</li>
          <li>Department hierarchy table</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">3</td>
      <td style="text-align:left">IFIX Core (Domain Services)</td>
      <td style="text-align:left">
        <ol>
          <li>IFIX Master Data Service
            <ol>
              <li>Government (_create and _search APIs)</li>
              <li>Chart Of Account (_create and _search APIs)</li>
              <li>Department (_create and _search APIs)</li>
              <li>Expenditure (_create and _search APIs)</li>
              <li>Project (_create and _search APIs)</li>
            </ol>
          </li>
          <li>IFIX Fiscal Event Service
            <ol>
              <li>Push fiscal event data (<code>_push</code> API)</li>
              <li>Search fiscal Event Data (<code>_search</code> API)</li>
            </ol>
          </li>
          <li>Fiscal Event Post Processor (Kafka to Data Store Sink and Druid Sink)</li>
          <li>Department Entity Service
            <ol>
              <li>Department Hierarchy (_create and _search APIs)</li>
              <li>Department Entity (_create and _search APIs)</li>
            </ol>
          </li>
          <li>Keycloak Setup</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">4</td>
      <td style="text-align:left">IFIX Adaptor</td>
      <td style="text-align:left">API for receiving data from client (mGramSeva - Water Bill/Receipt and
        Expense Bills) - events/v1/_push.</td>
    </tr>
  </tbody>
</table>

## Document Resources and Links

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>UI Technical Documents</b>
      </th>
      <th style="text-align:left"><b>Backend Service Documents</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p>mGgramSeva</p>
        <ul>
          <li>User Manual - Tech
            <ul>
              <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1922269185">Language Selection</a>
              </li>
              <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1922269219">Login</a>
              </li>
              <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1922662535">Update Password - FTL</a>
              </li>
              <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1922728099">Forgot Password</a>
              </li>
              <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1923416085">Home</a>
              </li>
              <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1925709827">Edit Profile</a>
              </li>
              <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1925546002">Change Password</a>
              </li>
              <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1925480514">Generate Bill</a>
              </li>
              <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1925316787">Search Connection</a>
              </li>
              <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1927348244">Consumer Creation</a>
              </li>
              <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1926791195">Update Consumer</a>
              </li>
              <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1926824121">Add Expenses</a>
              </li>
              <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1926791391">Search Expense Bills</a>
              </li>
              <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1927348594">Modify Expenses</a>
              </li>
              <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1926824058">Collections Dashboard</a>
              </li>
              <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1926791281">Expenditure Dashboard</a>
              </li>
              <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1928200243">Collect Payment</a>
              </li>
              <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1930526721">Consumer Feedback</a>
              </li>
            </ul>
          </li>
          <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1916207152"> Application Permissions and Dependencies</a>
          </li>
          <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1916239930">Application Structure</a>
          </li>
        </ul>
      </td>
      <td style="text-align:left">
        <p>IFIX Core (Domain Services)</p>
        <ul>
          <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1908801545">IFIX Master Data Service</a>
          </li>
          <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1914339339/iFIX+Fiscal+Event+Service"> IFIX Fiscal Event Service</a>
          </li>
          <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1917222977/iFIX+Fiscal+Event+Post+Processor"> IFIX Fiscal Event Post Processor</a>
          </li>
          <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1917157405/iFIX+Department+Entity+Service"> IFIX Department Entity Service</a>
          </li>
          <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1923088385">Keycloak Setup</a>
          </li>
        </ul>
        <p>IFIX Adaptor</p>
        <ul>
          <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1905950742"> IFIX Adapter Services v1.0</a>
          </li>
        </ul>
        <p>mGramSeva</p>
        <ul>
          <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1917190194">mGramSeva - Water Service</a>
          </li>
          <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1918566432">mGramSeva - Water Service Calculator</a>
          </li>
          <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1918369833">mGramSeva - eChallan Service</a>
          </li>
          <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1924300900">mGramSeva - User Service</a>
          </li>
          <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1926627396">mGramSeva - Billing Service</a>
          </li>
          <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1927348292">mGramSeva - User OTP</a>
          </li>
          <li><a href="https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1928626201">mGramSeva - IFIX Adapter Integration Service</a>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

