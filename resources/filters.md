# Filters

**NOT YET IMPLEMENTED** - still seeking comment on these from developers.

## Get current user's Filters

Return the <a href="/appdotnet/api-spec/blob/master/objects.md#filter">Filters</a> for the current user.

### URL
> https://api.app.net/stream/0/filters

### Parameters

None.

### Example

> GET https://api.app.net/stream/0/filters
```js
[
    {
        "id": "1",
        "type": "show",
        "name": "On the go",
        "user_ids": ["1", "2"],
        "hashtags": ["sf"],
        "link_domains": ["app.net"],
        "mention_user_ids": ["1"]
    },
    ...
]
```

## Create a Filter

Create a <a href="/appdotnet/api-spec/blob/master/objects.md#filter">Filter</a> for the current user.

### URL
> https://api.app.net/stream/0/filters

### Data

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Required?</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>filter</code></td>
            <td>Required</td>
            <td>string</td>
            <td>A JSON object representing the filter to create. See <a href="/appdotnet/api-spec/blob/master/objects.md#filter">the filter object</a> for more information. (Omit the <code>id</code> parameter).</td>
        </tr>
    </tbody>
</table>

### Example

> POST https://api.app.net/stream/0/filters
>
> POST DATA filter=%7B%27name%27%3A+%27On+the+go%27%2C+%27link_domains%27%3A+%5B%27app.net%27%5D%2C+%27hashtags%27%3A+%5B%27sf%27%5D%2C+%27user_ids%27%3A+%5B%271%27%2C+%272%27%5D%2C+%27mention_user_ids%27%3A+%5B%271%27%5D%2C+%27type%27%3A+%27show%27%2C+%27id%27%3A+%271%27%7D
```js
{
    "id": "1",
    "type": "show",
    "name": "On the go",
    "user_ids": ["1", "2"],
    "hashtags": ["sf"],
    "link_domains": ["app.net"],
    "mention_user_ids": ["1"]
}
```

## Retrieve a Filter

Returns a specific <a href="/appdotnet/api-spec/blob/master/objects.md#filter">Filter</a> object.

### URL
> https://api.app.net/stream/0/filters/[filter_id]

### Parameters

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Required?</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>filter_id</code></td>
            <td>Required</td>
            <td>string</td>
            <td>The filter id</td>
        </tr>
    </tbody>
</table>

### Example

> GET https://api.app.net/stream/0/filters/1
```js
{
    "id": "1",
    "type": "show",
    "name": "On the go",
    "user_ids": ["1", "2"],
    "hashtags": ["sf"],
    "link_domains": ["app.net"],
    "mention_user_ids": ["1"]
}
```

## Delete a Filter

Delete a <a href="/appdotnet/api-spec/blob/master/objects.md#filter">Filter</a>. The Filter must belong to the current User. It returns the deleted Filter on success.

### URL
> https://api.app.net/stream/0/[filter_id]

### Data

<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Required?</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>filter_id</code></td>
            <td>Required</td>
            <td>string</td>
            <td>The filter id</td>
        </tr>
    </tbody>
</table>

### Example

> DELETE https://api.app.net/stream/0/1
```js
{
    "id": "1",
    "type": "show",
    "name": "On the go",
    "user_ids": ["1", "2"],
    "hashtags": ["sf"],
    "link_domains": ["app.net"],
    "mention_user_ids": ["1"]
}
```
