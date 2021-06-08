Problem Statement:

Provided with the abundant data of Covid’19 effected countries, we are determined to estimate
the outbreak of this contagious virus for the next 10 days based on the reported data. Keeping
in view that the official confirmed cases number has surpassed all the previous prediction
(Anastassopoulou C 315), we would be applying two prediction model i.e. Linear Regression
and SVM model to compare the results and to provide the mortality rate.

Data Source:

Four datasets are used in the analyses and visualization of Covid’19 pandemic from the world's
largest data science source, Kaggle to demonstrate the outbreak worldwide. The Three global
dataset possess the comprehensive information of country/region, province/state, longitude and
latitude with their respective numbers of cases, deaths and recoveries from all regions of the
world ranging from 1/22/20 to 4/22/20. The covid19 confirmed global, covid19 deaths global,
covid19 recoveries global datasets are organized with rows representing the entries from
different countries and the columns depict the date in which cases are registered accordingly.
Each of the global dataset for a country are a time series. Let I be the Country/City and j the day.
A matrix of I by j dimensions would show the total cases against each Country/City on a
particular date.

The local dataset demonstrates the date wise entries of confirmed cases, deaths and recoveries
from different regions within Pakistan. It also shows the travel history, province and city name
to illustrate the reason behind the high peaks of confirmed cases which is mainly due to local
social contact and pilgrims from Tehran.
Active cases from the local dataset are calculate by using the formula:

                              Total active = Cases - (Deaths + Recovered)

For each of the city/province for active case visualization within Pakistan. To predict the
outbreak for future, following models are used.

Support Vector Machine:

An algorithm for two-group classification problems which is categorized under the supervised
machine learning approach. It is known as a Support Vector Machine. The model is used for
categorizing and predicting new data after training the SVM model with sets of labeled data.
Features:

1) This model works well with limited amount of data (thousands).

2) Takes in data points and gives out a hyper-plane that separates the classes i.e. it draws a
decision boundary between two sets of data.

3) It treats linear and non-linear data separately.

4) A simple linearly separable data works best in a 2D plane.


For non-linear data, it uses the kernel trick to differentiate among the data tags.

The kernel trick:
SVM model predictions include the conversion of data into multi-dimensions for fair
classification. Every step of transforming the data from lower dimension to a higher one involves
multiple steps of complicated calculation. It becomes expensive when every vector of the dataset
has to be transformed.

The kernel trick provides a cheaper solution and implements the dot product technique. The
kernel function takes input the data and transform in the required form. Kernel functions are of
different types:

1) Linear
2) Non-linear
3) Polynomial
4) Radial-Bias function
5) Sigmoid

Linear Regression Model:
It involves the fitting of linear equations to data and also models the relationship between two
variables. It is not necessary for the variables to be dependent on each other but some significant
association has to be there.
Linear regression line equation:

                                  Y = a + bX

Where, Y = explanatory variable, X = dependent variable. The slope of line is b and a is the
intercept.
Features:

1) It is commonly used for predictive analysis.
2) The predicted output values are continuous and form a slope.
3) It offers extrapolation technique when the prediction has to be made outside the range of actual
data.

Material and Methodology:

For the analysis of the world-wide data, we have coded in Python 3.0 by using Anaconda
Navigator 3 in Jupyter Notebook to process the data. The predominant libraries are matplotlib
that is responsible for creating a figure with respect to data provided in its function and other
legends and labels to make it more readable; seaborn that possesses a high level interface for
visualization of Covid’19 outbreak and its statistical information; sklearn library which
features multiple predictions models including SVM model by using SVR that is used to
predict future peaks in our analyses. mpl_toolkits.mplot3d library is used for 3d animation of
the model. Datetime and time libraries are added to rearrange the date format.

In our analysis of the local dataset, the data is grouped with respect to date, city and province
to illustrate the number of confirmed cases, recoveries and deaths. Univariate, Bivariate and
Multivariate analysis are done to find the correlation among features in local dataset using
heatmaps. Additionally, a 3d model is built to demonstrate the number of cases, death and
recoveries within Pakistan. A useful of FacetGrid is implemented to exhibit the effect of travel
history in the Covid’19 cases, carried out the function of sns.pairplot to get the histogram and
scatterplot of individual integer type feature in the set.
In the global dataset, illustrated the top 10 effected countries from this Covid’19 by country-
wise summation, grouped by dates using plt.barplots. Also, a pie chart is built to exemplify
the percentage of patients in each country.
To predict the outbreak for the next 10 days, we have used SVM and Linear Regression model
with test_split ratio of 0.15 and shuffle being False as the trend grows exponentially. Below
are the best suitable values for SVM features.
kernel = ['poly','sigmoid','rbf']
c = [0.01, 0.1, 1, 10]
gamma = [0.01, 0.1, 1]
epsilon = [0.01, 0.1, 1]
shrinking= [True, False]
SVM runs the model and chooses the best parameters out of those provided according to the data
it gets. Larger C tends to give an optimization result. Both values for shrinking is provided to
reduce the kernel dimensions depending upon the model. Svm_estimator plays a major role in
this infectious disease forecast as it returns the highest score of accuracy. We trained the model
using the original dates reported in the dataset and passed the next 10 days to the model to
predict the number of cases for future. Similarly, we fit the same x_train and y_train_confirmed
n the linear regression model with the same splitting ratio to get the linear prediction of future
for the next 10 days to have a comparative analysis.