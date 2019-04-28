# Genpact-Demand-Forecasting-Hackathon

</ul>
<h2><a id="user-content-problem-statement" class="anchor" aria-hidden="true" href="#problem-statement"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>Problem Statement</h2>
<p>Your client is a meal delivery company which operates in multiple cities. They have various fulfillment centers in these cities for dispatching meal orders to their customers. The client wants you to help these centers with demand forecasting for upcoming weeks so that these centers will plan the stock of raw materials accordingly.</p>
<p>The replenishment of majority of raw materials is done on weekly basis and since the raw material is perishable, the procurement planning is of utmost importance. Secondly, staffing of the centers is also one area wherein accurate demand forecasts are really helpful. Given the following information, the task is to predict the demand for the next 10 weeks (Weeks: 146-155) for the center-meal combinations in the test set:</p>
<ul>
<li>Historical data of demand for a product-center combination (Weeks: 1 to 145)</li>
<li>Product(Meal) features such as category, sub-category, current price and discount</li>
<li>Information for fulfillment center like center area, city information etc.</li>
</ul>
<h2><a id="user-content-data-dictionary" class="anchor" aria-hidden="true" href="#data-dictionary"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>Data Dictionary</h2>
<ol>
<li><strong>Weekly Demand data (train.csv)</strong>: Contains the historical demand data for all centers, test.csv contains all the following features except the target variable.</li>
</ol>
<table>
<thead>
<tr>
<th>Variable</th>
<th>Definition</th>
</tr>
</thead>
<tbody>
<tr>
<td>id</td>
<td>Unique ID</td>
</tr>
<tr>
<td>week</td>
<td>Week No</td>
</tr>
<tr>
<td>center_id</td>
<td>Unique ID for fulfillment center</td>
</tr>
<tr>
<td>meal_id</td>
<td>Unique ID for Meal</td>
</tr>
<tr>
<td>checkout_price</td>
<td>Final price including discount, taxes &amp; delivery charges</td>
</tr>
<tr>
<td>base_price</td>
<td>Base price of the meal</td>
</tr>
<tr>
<td>emailer_for_promotion</td>
<td>Emailer sent for promotion of meal</td>
</tr>
<tr>
<td>homepage_featured	Meal</td>
<td>featured at homepage</td>
</tr>
<tr>
<td>num_orders</td>
<td>(Target) Orders Count</td>
</tr>
</tbody>
</table>
<ol start="2">
<li><strong>fulfilment_center_info.csv</strong>: Contains information for each fulfilment center</li>
</ol>
<table>
<thead>
<tr>
<th>Variable</th>
<th>Definition</th>
</tr>
</thead>
<tbody>
<tr>
<td>center_id</td>
<td>Unique ID for fulfillment center</td>
</tr>
<tr>
<td>city_code</td>
<td>Unique code for city</td>
</tr>
<tr>
<td>region_code</td>
<td>Unique code for region</td>
</tr>
<tr>
<td>center_type</td>
<td>Anonymized center type</td>
</tr>
<tr>
<td>op_area</td>
<td>Area of operation (in km^2)</td>
</tr>
</tbody>
</table>
<ol start="3">
<li><strong>meal_info.csv</strong>: Contains information for each meal being served</li>
</ol>
<table>
<thead>
<tr>
<th>Variable</th>
<th>Definition</th>
</tr>
</thead>
<tbody>
<tr>
<td>meal_id</td>
<td>Unique ID for the meal</td>
</tr>
<tr>
<td>category</td>
<td>Type of meal (beverages/snacks/soups….)</td>
</tr>
<tr>
<td>cuisine</td>
<td>Meal cuisine (Indian/Italian/…)</td>
</tr>
</tbody>
</table>
<h2><a id="user-content-evaluation-metric" class="anchor" aria-hidden="true" href="#evaluation-metric"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>Evaluation Metric</h2>
<p>The evaluation metric for this competition is <strong>100*RMSLE</strong> where RMSLE is Root of Mean Squared Logarithmic Error across all entries in the test set.</p>
<p>Test data is further randomly divided into Public (30%) and Private (70%) data.</p>
