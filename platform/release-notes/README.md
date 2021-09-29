# Release Notes

## Release Summary

IFIX 1.0-alpha is a release that has got a new module, a few functional changes, and non-functional changes.

* Functional: mGramSeva application and Reference Dashboard
* Non-functional: IFIX Core \(Domain Services\) and IFIX Adaptor

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
            Update Profile)</li>
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
          <li>Localization support in English, Hindi, and Punjabi for Labels, messages,
            SMS Notifications, Master data, and PDFs</li>
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
        Expense Bills) - events/v1/_push</td>
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
        <p><a href="../../exemplar/mgramseva/">mGgramSeva</a>
        </p>
        <ul>
          <li> <a href="../../exemplar/mgramseva/user-manual/tech-user-manual/">User Manual - Tech</a>
            <ul>
              <li><a href="../../exemplar/mgramseva/user-manual/tech-user-manual/language-selection.md">Language Selection</a>
              </li>
              <li><a href="../../exemplar/mgramseva/user-manual/tech-user-manual/login.md">Login</a>
              </li>
              <li><a href="../../exemplar/mgramseva/user-manual/tech-user-manual/update-password-ftl.md">Update Password - FTL</a>
              </li>
              <li><a href="../../exemplar/mgramseva/user-manual/tech-user-manual/forgot-password.md">Forgot Password</a>
              </li>
              <li><a href="../../exemplar/mgramseva/user-manual/tech-user-manual/home.md">Home</a>
              </li>
              <li><a href="../../exemplar/mgramseva/user-manual/tech-user-manual/edit-profile.md">Edit Profile</a>
              </li>
              <li><a href="../../exemplar/mgramseva/user-manual/tech-user-manual/change-password.md">Change Password</a>
              </li>
              <li><a href="../../exemplar/mgramseva/user-manual/tech-user-manual/generate-bill.md">Generate Bill</a>
              </li>
              <li><a href="../../exemplar/mgramseva/user-manual/tech-user-manual/search-connection.md">Search Connection</a>
              </li>
              <li><a href="../../exemplar/mgramseva/user-manual/tech-user-manual/consumer-details/create-consumer.md">Consumer Creation</a>
              </li>
              <li><a href="../../exemplar/mgramseva/user-manual/tech-user-manual/consumer-details/update-consumer.md">Update Consumer</a>
              </li>
              <li><a href="../../exemplar/mgramseva/user-manual/tech-user-manual/expenses/add-expenses.md">Add Expenses</a>
              </li>
              <li><a href="../../exemplar/mgramseva/user-manual/tech-user-manual/expenses/search-expense-bills.md">Search Expense Bills</a>
              </li>
              <li><a href="../../exemplar/mgramseva/user-manual/tech-user-manual/expenses/modify-expenses.md">Modify Expenses</a>
              </li>
              <li><a href="../../exemplar/mgramseva/user-manual/tech-user-manual/dashboard/collections-dashboard.md">Collections Dashboard</a>
              </li>
              <li><a href="../../exemplar/mgramseva/user-manual/tech-user-manual/dashboard/expenditure-dashboard.md">Expenditure Dashboard</a>
              </li>
              <li><a href="../../exemplar/mgramseva/user-manual/tech-user-manual/collect-payment.md">Collect Payment</a>
              </li>
              <li><a href="../../exemplar/mgramseva/user-manual/tech-user-manual/consumer-feedback.md">Consumer Feedback</a>
              </li>
            </ul>
          </li>
          <li><a href="../../exemplar/mgramseva/user-manual/mgramseva-ui/application-permissions.md"> Application Permissions and Dependencies</a>
          </li>
          <li><a href="../../exemplar/mgramseva/user-manual/tech-user-manual/application-structure.md">Application Structure</a>
          </li>
        </ul>
      </td>
      <td style="text-align:left">
        <p><a href="../architecture/services/">IFIX Core (Domain Services)</a>
        </p>
        <ul>
          <li><a href="../architecture/services/master-data-service.md">IFIX Master Data Service</a>
          </li>
          <li><a href="../architecture/services/fiscal-event-service.md"> IFIX Fiscal Event Service</a>
          </li>
          <li><a href="../architecture/services/untitled.md"> IFIX Fiscal Event Post Processor</a>
          </li>
          <li><a href="../architecture/services/department-entity-service.md"> IFIX Department Entity Service</a>
          </li>
          <li><a href="../architecture/services/keycloak-setup.md">Keycloak Setup</a>
          </li>
        </ul>
        <p><a href="../../exemplar/ifix-adapter/">IFIX Adaptor</a>
        </p>
        <ul>
          <li><a href="../../exemplar/ifix-adapter/adapter-services.md"> IFIX Adapter Services v1.0</a>
          </li>
        </ul>
        <p><a href="../../exemplar/mgramseva/">mGramSeva</a>
        </p>
        <ul>
          <li><a href="../../exemplar/mgramseva/user-manual/backend-services/water-services.md">mGramSeva - Water Service</a>
          </li>
          <li><a href="../../exemplar/mgramseva/user-manual/backend-services/water-service-calculator.md">mGramSeva - Water Service Calculator</a>
          </li>
          <li><a href="../../exemplar/mgramseva/user-manual/backend-services/e-challan-service.md">mGramSeva - eChallan Service</a>
          </li>
          <li><a href="../../exemplar/mgramseva/user-manual/backend-services/user-service.md">mGramSeva - User Service</a>
          </li>
          <li><a href="../../exemplar/mgramseva/user-manual/backend-services/billing-service.md">mGramSeva - Billing Service</a>
          </li>
          <li><a href="../../exemplar/mgramseva/user-manual/backend-services/mgramseva-user-otp.md">mGramSeva - User OTP</a>
          </li>
          <li><a href="../../exemplar/mgramseva/user-manual/backend-services/ifix-adapter-integration-service.md">mGramSeva - IFIX Adapter Integration Service</a>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

