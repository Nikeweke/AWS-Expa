## AWS DynamoDB

* [Add `updatedAt` to value](https://github.com/Nikeweke/AWS-Expa/blob/main/dynamo-db.md#add-updatedat-to-value)

--- 

### Add `updatedAt` to value 

> Here is `#val` is value alias and its adding to projects with `updateAt` and works fine

```typescript
const params: DocumentClient.QueryInput = {
  TableName: dynamoDBService.getTableName(),
  ProjectionExpression: 'updatedAt, settingKey, familyIdUserId, #val',
  ExpressionAttributeNames: {
    '#val': 'value',
  },
  KeyConditionExpression: 'familyIdUserId = :familyIdUserId AND settingKey = :settingKey',
  ExpressionAttributeValues: {
    ':familyIdUserId': userId ? ${familyId}:${userId} : familyId,
    ':settingKey': settingKey,
  },
};
```
<br />
