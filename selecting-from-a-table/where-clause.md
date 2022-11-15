# Where clause

Burada isə biz select statemntsdə `where`  şərtinə baxacağıq. Burada biz customer tabledə bütün məlumatları select edirik. Bunun üçün ulduzdan istifadə edirik. Və nəticədə cusotmer də nə məlumat varsa hamsı qaydıır.&#x20;

Bəs mən ancaq istədiyim bir rov nu yəni stəri gətirmək istəsəm nə emtəliyəm. Gəlin dəqiqləşdirək, mən anca Babayev soyadlı şəxsləri axtarmaq istəyirəmş. Bunun üçün biz sorğumuza vhere şərtini əlavə edirik.

![](<../.gitbook/assets/image (5).png>)

So here I have selected star from products,

and I'm going to add a where clause which will mean

that it's only going to return

rose where coffee origin is equal to Colombia.

So to add a where clause,

we need to type select star from products.

And then on the next line, we need to type where

a column is equal to a certain value.

So you put where followed by the column name.

So in this case, it's coffee origin

is equal to a certain value.

So in this case, I want to be to be equal to Colombia.

So for varchar or char data types, I need to use single quotes.

And then within those single quotes, I need to type the value so. In this case,it's Colombia.

And then I can run that. So we've got select star from products

where coffee origin column is equal to Colombia.

And you can see that's just returned

the first two rows where coffee origin was equal to Colombia.

Now we can also do it with

integers or numbers.

So let's try the price column now. So let's type where price

is equal to three dollars or 3.00.

Now because it's a number we don't have to use single quotes,

we can just type 3.00.

And we see we have

our two products where the price was equal to 3.00.

So that's how we use where clauses in select statements.

And we can also have more than one where clause in a single select statement.

So here I've just got one where clause.

So I've got where price is equal to 3.00,

but I can also add a second one by going to the next line and typing

and then putting my next where clause.

So I type and column name equal to a certain value.

So let's type where price is equal to 3.00

and coffee origin is equal to Colombia.

And because it's a string we have single quotes

and let's run that and see what we get.

And you can see it returns one row which meets both where clauses.

So we have a price that's equal to 3.00

and we also have an origin that's equal to Colombia.

And we can keep going

adding more and more where clauses as many as we want.

We just have to keep typing ands

column name equal to a certain value and column name equal to certain value

for as long as you want, for as many where clauses as you want.

As well as using the and

statement, we can also use or.

So we can say select star from products

where price is equal to 3.00

or coffee origin is equal to Colombia.

And if we run that, let's see what we get.

So you can see here it's returned all the rows

which meet either one or both of the criterias.

So here we've got both our coffee origins which are equal to Colombia.

But you can see it's also included the espresso,

which has a price of 2.5, so that didn't meet

the price is equal to 3.0 but it did meet the coffee origin is equal to Colombia.

And then similarly here, we have the filter coffee

which does have a price of 3.00,

but it doesn't have a coffee origin of Sri Lanka.

So that all means it only has to meet one of the where clauses

but the and it has to meet both of the where clauses.

So that's it for adding a simple where clause to our select statement.

We just have to type where column name is equal to a certain value,

and we can add as many where clauses as we want

using the and or the or statement.

So let's move on to the next video.
