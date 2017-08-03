# __���������������ĵ�__

## __��ѯ�˺���Ϣ__

```http
GET /getAccount?address=a002423c235a7ba9649347ff85b6be1c51980d1eff0398&key=hello&code=xxx&issuer=xxx
```

|����|����
|:--- | --- 
| address | �˺ŵ�ַ�� ����
| key | �˺ŵ� metadata ��ָ����key��ֵ���������д����ô���ؽ���к������е�metadata
| code |�ʲ�����
| issuer | �ʲ�������

�ʲ�������ʲ�����������������Ҫôͬʱ��д��Ҫôͬʱ����д��������д�����صĽ���а������е��ʲ���

```json
{
  "error_code" : 0,
  "result" : {
    "address" : "a002423c235a7ba9649347ff85b6be1c51980d1eff0398",
    "assets" : [{
        "amount" : 1400,
        "property" : {
          "code" : "CNY",
          "issuer" : "a002423c235a7ba9649347ff85b6be1c51980d1eff0398"
        }
      }, {
        "amount" : 1000,
        "property" : {
          "code" : "USD",
          "issuer" : "a002423c235a7ba9649347ff85b6be1c51980d1eff0398"
        }
      }, {
        "amount" : 3000,
        "property" : {
          "code" : "zichanpingzheng",
          "issuer" : "a002943cede1be5fb0ca0da9f9b49b0ce20b613357524a"
        }
      }, {
        "amount" : 3000,
        "property" : {
          "code" : "CNY",
          "issuer" : "a002abcecded14a3068d2c535324980f41c7aeb8bf144c"
        }
      }
    ],
    "assets_hash" : "9696b03e4c3169380882e0217a986717adfc5877b495068152e6aa25370ecf4a",
    "contract" : null,
    "metadatas" : [{
        "key" : "123",
        "value" : "123_value",
        "version" : 1
      }, {
        "key" : "456",
        "value" : "456_value",
        "version" : 1
      }, {
        "key" : "abcd",
        "value" : "abcd_value",
        "version" : 1
      }
    ],
    "nonce" : 1,
    "priv" : {
      "master_weight" : "1",
      "thresholds" : {
        "tx_threshold" : "1"
      }
    },
    "storage_hash" : "82c8407cc7cd77897be3100c47ed9d43ec4097ee1c00e2c13447187e5b1ac66c"
  }
}


```
- ������˻�������,�򷵻�����

```json
{
   "error_code" : 4,
   "result" : null
}
```


## __��ѯledger__
```http
GET /getLedger?seq=xxxx&with_validator=true&with_consvalue=true
```
|����|����
|:--- | --- 
|seq  | ledger����ţ� �������д�����ص�ǰledger
|with_validator | true or false,������֤�ڵ��б�
|with_consvalue | true or fasse,������ʶvalue

- �����ѯ��ledger�򷵻�����:

```json
{
   "error_code" : 0,
   "result" : {
      "header" : {
         "account_tree_hash" : "945c729a8dace879bfca6d88077a6c7c6f1ffec55bb7b9398dde2e31c223905e",
         "close_time" : 1499682806032615,
         "consensus_value_hash" : "f418eefca74cbe95b1cda2cc3c20504dc90e9bcd1d995c8642c831c6bce91211",
         "hash" : "bfd1ca75335790b0f0e2dbbf822c09ddb73520abc314e56345466d17b8323d6a",
         "previous_hash" : "f1a586ba5d92b4aab10e40f424621a9ff284c07ae1e683d7036102d63a2e297c",
         "seq" : 6,
         "validators_hash" : "f8fa66d831ab39ea149525211e1a939b8d9fafbb19f7c4d6a4de18f998884f4c",
         "version" : 3000
      },
      "validators" : {
         "validators" : [
            "a0024740b934765287b16113adc6bb285d72c124d9e3c1",
            "a0022df150ad08ab8c238a44844bfe6f4f6576c1ab35c4"
         ]
      }
      ,
      "consensus_value" :{...}
   }
}
```

- ���û�в�ѯ��ledger���ص�����:

``` json
{
   "error_code" : 4,
   "result" : null
}
```

## __��ѯ����__

```http
GET /getTransactionHistory?hash=ad545bfc26c440e324076fbbe1d8affbd8a2277858dc35927d425d0fe644e698
```

|����|����
|:--- | --- 
|hash | ���׵�hash���ǽ��׵�Ψһ��ʶ
|ledger_seq | ledger�����

����ʾ��
```json
{
   "error_code" : 0,
   "result" : {
      "total_count" : 1,
      "transactions" : [
         {
            "close_time" : 1496652785322300,
            "error_code" : 0,
            "ledger_seq" : 8,
            "signatures" : [
               {
                  "public_key" : "b0020413806c5dd6fd473ab3ea7c484453ba2c07b41ff4d13832a49488bc3eec27c25f5c9f477eeb0e9953de10a8f3df956a979f4750b51efc59db6e7c2a998fdbda0acd",
                  "sign_data" : "4b5c4efb4f51a46fc1aa3989debf9fb02e4a9913f67f0fa796b704988ff97f037436669ba7d17a60c96a0c53d4a3bb7913c0c5dcfd29b2abac0ad9d8f58c0c78"
               },
               {
                  "public_key" : "b002043891953ca02a9decd4d5050385332b6599b11f2a2d34ee8edec541611b6e29e7ca992cf1998fb1fc41f51af30525d6e1119dfec74bf3405341b0eb79ee564ab7ce",
                  "sign_data" : "0bf9f4557150f894ddbc6b7bdce71b3b5fab7b761896a6a0c92d2a01956cdf44d423994e50b22704d0b43f62f0cd6caef6fdc223d4d9ef1e88b8644a250a66df"
               },
               {
                  "public_key" : "b002046ea5264d68f4407c7d449612b94f7603a50bd2e75ee9458c7b720b185e0be54986e7f9d9f6571434f7cb335e00be34addd16ce998a01a073db880a8262743f8a42",
                  "sign_data" : "7f82bffe5f9603728e341f3cdfa85d03523b6f9345ef0c5cb23076db091ddb124f96e5b23c5bf32fca7a77319333b789c22b370d556ae7543e12a96814294872"
               }
            ],
            "transaction" : {
               "nonce" : 1,
               "operations" : [
                  {
                     "create_account" : {
                        "dest_address" : "a002abcecded14a3068d2c535324980f41c7aeb8bf144c"
                     },
                     "type" : 1
                  },
                  {
                     "create_account" : {
                        "dest_address" : "a002943cede1be5fb0ca0da9f9b49b0ce20b613357524a"
                     },
                     "type" : 1
                  },
                  {
                     "create_account" : {
                        "dest_address" : "a002385d3017771162b353e9af4c11edb66c665abcfcb6"
                     },
                     "type" : 1
                  },
                  {
                     "create_account" : {
                        "dest_address" : "a002423c235a7ba9649347ff85b6be1c51980d1eff0398"
                     },
                     "type" : 1
                  },
                  {
                     "issue_asset" : {
                        "amount" : 10000000,
                        "code" : "CNY"
                     },
                     "source_address" : "a002abcecded14a3068d2c535324980f41c7aeb8bf144c",
                     "type" : 2
                  }
               ],
               "source_address" : "a0025e6de5a793da4b5b00715b7774916c06e9a72b7c18"
            }
         }
      ]
   }
}
```

����ý��ײ������򷵻�

```json
{
   "error_code" : 4,
   "result" : {
      "total_count" : 0,
      "transactions" : []
   }
}
```

## __������֤�ڵ�__

```http
POST /confValidator?add=a00252641e461a28e0f2d19e01fa9ce4ba89af24d5f0c6&&del=a0027fb6fd8e8ffbf64cf10efebd9278735d5e39a6325e
```

|����|����
|:--- | --- 
|add |���ŷָ�����Ҫ��ӵ���֤�ڵ��б�
|del |���ŷָ�����Ҫɾ������֤�ڵ��б�

ע����Ҫ�󲿷ֵ���֤�ڵ㶼ִ����ӡ�ɾ���������ҹ�ʶ�ɹ��������ӡ�ɾ���ɹ�


## __��ȡ�������л�����__

|����|����
|:--- | --- 
|source_address |���׷����ߵĵ�ַ
|nonce |��ţ��൱��seq��ͨ��getAccount��ȡ�����û����Ϊ0
|operations | �����б�

```http
POST /getTransactionBlob
```

```json
{
  "source_address" : "a0025e6de5a793da4b5b00715b7774916c06e9a72b7c18",
  "nonce" : 130,
  "operations" : [{
      "ps" : "���ݲ�ͬ�Ĳ���������д"
    }, {
      "ps" : "���ݲ�ͬ�Ĳ���������д"
    }
  ]
}
```


## __�ύ����__

|����|����
|:--- | --- 
|transaction_blob| �������л�֮���16���Ƹ�ʽ
|sign_data| ǩ��16���Ƹ�ʽ
|public_key| ��Կ

```http
POST /submitTransaction
```

```json
{
  "items" : [{
      "transaction_blob" : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
      "signatures" : [{
          "sign_data" : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
          "public_key" : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
        }, {
          "sign_data" : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
          "public_key" : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
        }
      ]
    }
  ]
}
```

### __�����ֶι����ֶ�__

|����|����
|:--- | --- 
|source_address | ���׷����˵�ַ�� required
|nonce| �������,required
|expr_condition|���ʽ�ֶ�, optional
|metadata|���׵�Ԫ����, optional

### expr_condtion ���ʽ����
�ñ��ʽ�ֶΣ������Զ��彻����Ч���򣬱������ý�����ĳ���˻���master_weight ���� 100 ��Ч�����
jsonpath(account(\"bubiV8i6mtcDN5a1X7PbRPuaZuo63QRrHxHGr98s\"), \".priv.master_weight\") > 100

#### expr_condtion�ڲ�����


|����|����
|:--- | --- 
|account(address)| ��ȡ�˻���Ϣ, ���� json ���л��ַ���
|ledger(nonce) | ��ȡ������Ϣ, ���� json ���л��ַ���
|jsonpath(json_string, path)| ��ȡjson���������ֵ 
|LEDGER_SEQ| ���ñ������������µ�����߶�
|LEDGER_TIME|���ñ������������µ���������ʱ��

### ����

������4����ͬ����

|����|����
|:--- | --- 
|source_address| ָ�ĸ��˺����˲���,��Ϊ�ջ���д��Ĭ���뽻�׷�������ͬ�� optional
|type|��ʾ�ò��������ͣ� required
|metadata|������ metadata ֵ��16���Ʊ�ʾ�� optional
|expr_condition|�����ı��ʽ���ƣ� optional


#### ��������
�������ʹ��� | ������������ | ˵��
|:--- | --- | --- |
1 | �����ʺ� | �����½��ʺ�
2 | �����ʲ� | 
3 | ת���ʲ� | ���ô˽ӿڿ��Խ��Զ����ʲ�ת����һ���ʺ�
4 | ����metadata     |  �����˺����� key / value ֵ
5 | ����Signer Weight | �����˺�Ȩ�أ�����master �� signer
6 | ����Threshold | ��������ֵ������Ĭ�����޻�����������
7 | ���ú�Լ


#### 1. �����˺�

|����|����
|:--- | --- 
|dest_address |  �˺ŵĵ�ַ
|contract|  �������д����ô����һ����ͨ���˺š������д����ô����һ����Լ�˺�
| priv|  ���˺ŵ�Ȩ����Ϣ

```json

 {
   "type" : 1,
   "create_account" :
   {
     "dest_address" : "a0026f43f60f511c8260b9ded0c830de6109b3bbeb06c7", //required
     "contract" : //optional
     {
       "contract_id" : "something identify this contract",
       "payload" : "function Main(input) {  var a = callBackGetAccountInfo('a0025e6de5a793da4b5b00715b7774916c06e9a72b7c18');  if (a) callBackLog(a);  var b = callBackGetAccountMetaData('a0025e6de5a793da4b5b00715b7774916c06e9a72b7c18', input['key']);  if (b) callBackLog(b);  var tx = { 'operations' : [{ 'type' : 'ISSUE_ASSET', 'source_address' : 'a0025e6de5a793da4b5b00715b7774916c06e9a72b7c18', 'issue_asset' : {  'code' : 'cny',  'amount' : input.amount }  } ]  };  callBackDoOperation(tx); } "
     },
     "metadatas" : [
        {
          "key" : "111",
          "value" : "hello 111!",
          "version" : 0
        },
        {
          "key" : "222",
          "value" : "hello 222!",
          "version" : 0
        }
     ],
     "priv" :  //required
     {
       "master_weight" : 10, //optional, default 0, [0, MAX(UINT32)]
       "signers" : [      //optional
         {
           "address" : "a002d225e3e52fa8b341105d2109c0be0a90749ee42b21",
           "weight" : 6
         }
       ],
       "thresholds" : //required
       {
         "tx_threshold" : 7, //optional,  default 0, [0, MAX(INT64)]
         "type_thresholds" : [  //optional
           {
             "type" : 1,
             "threshold" : 8
           },
           {
             "type" : 2,
             "threshold" : 5
           }
         ]
       }
     }
   }
 }
```

#### 2. �����ʲ�

```json

{
  "type" : 2,
  "issue_asset" :
  {
    "amount" : 1000,
    "code" : "CNY"
  }
}
```


#### 3. ת���ʲ�/���ú�Լ
�ò����Ȱ�ָ�����ʲ�ת��Ŀ���˺ţ�Ȼ�����Ŀ���˺ŵĺ�Լ���벢��input��Ϊ��Ρ�
��Ŀ���˺�û�к�Լ���룬��ֻ����ת���ʲ�������

```json

{
  "type" : 3,
  "payment" :
  {
    "dest_address" : "a002f22d29d38b3a4f0afb3689f24c580529c05454a20c",
    "asset" :
    {
      "property" :
      {
        "issuer" : "a002d5905562ba1a32d7879c73131d68c5814526ff62b4",
        "code" : "CNY"
      },
      "amount" : 100
    },
    "input":"{\"bar\":\"foo\"}"
  }
}
```


#### 4. ����metadata
�����˺ŵ�metadata���ԣ�metadata ��һ��key-value �ṹ���ɴ洢�����ֵ�ԡ�

|����|����
|:--- | --- 
| key  |required��length:(0, 256]
| value  |optional��length:(0, 1048576]
| version |optional��default 0, 0�������ư汾��>0 : ��ǰ value �İ汾����Ϊ��ֵ�� <0 : �Ƿ�

ÿ�ο����ö����

```json
{
  "type" : 4,
  "set_metadata" :
      {
        "key" : "abc",
        "value" : "hello abc!",
        "version" : 0
      }
}
```
---

#### 5. ����Signer Weight
�����˺ŵ�ǩ������
- master_weight optional��default 0�� -1 �� �����ø�ֵ��0������masterȨ��ֵΪ0�� >0 && <= MAX(UINT32)������Ȩ��ֵΪ��ֵ���������Ƿ�
- address ��Ҫ������ signer ��ַ�����ϵ�ַУ�����
- weight  optional��default 0, 0 ��ɾ����signer��>0 && <= MAX(UINT32)������Ȩ��ֵΪ��ֵ���������Ƿ�

```json
{
    "type" : 5,
    "set_signer_weight" : { 
         "master_weight" : 2, 
         "signers" : [ 
            { 
               "address" : "a002ebe7a1c703f90f1c7ecdd7bc6bc4b3ab01f3563f80", 
               "weight" : 2 
            } 
         ] 
      }
}
```

#### 6. ����Threshold
�����˺Ų�����Ȩ��

|����|����
|:--- | --- 
|tx_threshold |optional��default 0, ��ʾ���˺ŵ����Ȩ�ޣ�-1: ��ʾ�����ø�ֵ��>0 && <= MAX(INT64)������Ȩ��ֵΪ��ֵ���������Ƿ�
|type |��ʾĳ�����͵Ĳ���  (0, 100]
|threshold | optional��default 0, 0 ��ɾ�������Ͳ�����>0 && <= MAX(INT64)������Ȩ��ֵΪ��ֵ���������Ƿ�

```json
{
    "type" : 6,
    "set_threshold": {
        "tx_threshold": 7,
        "type_thresholds":[
            {
                "type":1,
                "threshold":8
            },
            {
                "type":2,
                "threshold":5
            }
        ]  
    }
}
```

# __���д��Լ__
��Լ��һ��JavaScript���룬ϵͳҪ��ʵ��main�������ú���Ҳ�Ǻ�Լִ�й����е���ں�����
�ú�����������ַ���input���ǵ��øú�Լ��ʱ��ָ���ġ�

������һ���򵥵�����

```javascript
function foo(bar)
{
  /*do whatever you want*/

}

function main(input)
{
  var para = JSON.parse(input);
  if (para.do_foo)
  {
    var x = {
      'hello' : 'world'
    };
    foo(x);
  }
}
```

ϵͳ�ṩ�˼���ȫ�ֺ���, ��Щ�������Ի�ȡ��������һЩ��Ϣ��Ҳ�������˺ŷ�����

### 1. ��ȡ�˺���Ϣ(������metada���ʲ�)

callBackGetAccountInfo(address);
- address: �˺ŵ�ַ

����
``` javascript
var account = callBackGetAccountInfo('a0025e6de5a793da4b5b00715b7774916c06e9a72b7c18');
/*
account�������¸�ʽ
 {
    "address": "a002943cede1be5fb0ca0da9f9b49b0ce20b613357524a",
    "assets_hash": "5aef61a8988ce2be1da67cf4b37717748c352b8e4a0bdad2ad0964f80aca0101",
    "contract": null,
    "priv": null,
    "storage_hash": "e4775fb7fc2a5a06a4bbe0e63f362f8e24ff7752f0259ccd2fe1fc2e6e68781a"
  }
*/
```

### 2. ��ȡĳ���˺ŵ�metadata��Ϣ
callBackGetAccountMetaData(account_address, metadata_key);
- account_address: �˺ŵ�ַ
- metadata_key�� metadata��key

����
```javascript
var bar = callBackGetAccountMetaData('a0025e6de5a793da4b5b00715b7774916c06e9a72b7c18','abc');
/*
 bar��ֵ�����µĸ�ʽ
 {
     'key':'abc',
     'value':'hello world',
     'version':12
 }
*/

```
���ɵõ��˺�a0025e6de5a793da4b5b00715b7774916c06e9a72b7c18��metadata��abc��ֵ

### 3.  ��ȡĳ���˺ŵ��ʲ���Ϣ
callBackGetAccountAsset(account_address, asset_property);

- account_address: �˺ŵ�ַ
- asset_property�� �ʲ�����

����
```javascript
var asset_property =
{
  'issuer' : 'a002bbe0b6f547d6bec2c83fb9bb93e75d37c1755f2de6',
  'code' : 'CNY'
};
var bar = callBackGetAccountAsset('a0025e6de5a793da4b5b00715b7774916c06e9a72b7c18', asset_property);

/*
{
  "amount": 1,
  "property": {
    "code": "CNY",
    "issuer": "a002bbe0b6f547d6bec2c83fb9bb93e75d37c1755f2de6"
  }
}
*/
```

### 4.  ��ȡ����
callBackGetTransactionInfo(hash);
- hash: ����hash

����
```javascript
var tx = callBackGetTransactionInfo('ea565a904d568368f4ab556bb20c3f3933411f72ef487e8f73eddbc6d7b84565');
```

### 5. ��ȡ������Ϣ
callBackGetLedgerInfo(ledger_seq);
- ledger_seq: �����

����
```javascript
var ledger = callBackGetLedgerInfo(40);
/*
ledger�������¸�ʽ
{
    "account_tree_hash": "af05a60772cfd39f3b7838f4032f50450c100dedddf88e0132066688f6ae5c14",
    "consensus_value": {
      "close_time": 1495855656157405,
      "payload": "240398d89a5efba398fefb0dc194b45abe7b9dbc35326ee8238fff6633371004"
    },
    "hash": "9f82d8ad1c381e1ce2ce00c559fb2cf3a386d79e9414e92ce3ed809258913384",
    "ledger_sequence": 40,
    "ledger_version": 1000,
    "previous_hash": "3ff9b79479d62e7c52f2c0ab08598d219ffd4403bd5c1337764d3591e9b0ba24",
    "transaction_tree_hash": "e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855",
    "tx_count": 34359738368
  }
*/

```

### 6.  �ú�Լ�˺ŵĵ�ַ
ȫ�ֱ���  ThisAddress

ȫ�ֱ���ThisAddress��ֵ���ڸú�Լ�˺ŵĵ�ַ��

�����˺�x������һ�ʽ��׵��ú�ԼY������ִ�й����У�ThisAddress��ֵ����Y��Լ�˺ŵĵ�ַ��

```javascript
var bar = ThisAddress;
/*
bar��ֵ��Y��Լ���˺ŵ�ַ��
*/
```

### 7.  �����ߵĵ�ַ
ȫ�ֱ���  Sender

ȫ�ֱ���Sender��ֵ���ڱ��ε��øú�Լ���˺š�

����ĳ�˺ŷ�����һ�ʽ��ף��ý������и������ǵ��ú�ԼY���ò�����source_address��x������ô��ԼYִ�й����У�Sender��ֵ����x�˺ŵĵ�ַ��

```javascript
var bar = Sender;
/*
��ôbar��ֵ��x���˺ŵ�ַ��
*/
```


### 8.  ������
���Լ�˺���һ�ʽ��ף������������һ��������source_address�����Զ���ɺ�Լ�˺š�
����source_address�ǲ���Ҫ��д�ģ���ʹ��дҲ���á�

callBackDoOperation(transaction);
- transaction: ��������
����: true/false



����
```javascript
var transaction =
{
  'operations' :
  [
    {
      "type" : "ISSUE_ASSET",
      "issue_asset" :
      {
        "amount" : 1000,
        "code" : "CNY"
      }
    }
  ]
};

var result = callBackDoOperation(transaction);
```

### 9.  ���ñ���Լ�˺ŵ�metadata
callBackSetAccountMetaData(KeyPair);
- KeyPair: Ҫ���õ�����
����:true/false
����

```javascript
var KeyPair =
{
  'key' : 'abc',
  'value' : 'hello',
  'version' : 2
};

var result = callBackSetAccountMetaData(KeyPair);
```

**ע��: �˺����൱�ں�Լ�˺ŷ���һ�ʽ��ף��ý��׵Ĳ��������������metadata��** 

���������÷��ȼۣ�

```javascript
var transaction =
{
  'operations' :
  [
    {
      "type" : "SET_METADATA",
      "set_metadata" :
      {
        'key' : 'abc',
        'value' : 'hello',
        'version' : 2
      }
    }
  ]
};

var result = callBackDoOperation(transaction);
```
����```version```���Բ���д��
- ���version��ֵ�Ҳ�Ϊ0����ֵ��Ҫ�͵�ǰ��versionƥ��������óɹ���
- �������д��versionΪ0����ôϵͳ����Ҫƥ�䵱ǰversion�������óɹ���

## __������__
�����������ֹ���:
- error_code : �����룬��ŵĴ������
- error_desc : ����������һ���ܴӴ�������׼ȷ���ִ��������Ϣ

�����б����£�

error_code | enum | error_desc
|:--- | --- | --- |
0  | ERRCODE_SUCCESS | �����ɹ�
1  | ERRCODE_INTERNAL_ERROR | �����ڲ�����
2  | ERRCODE_INVALID_PARAMETER | ��������
3  | ERRCODE_ALREADY_EXIST | �����Ѵ��ڣ� ���ظ��ύ����
4  | ERRCODE_NOT_EXIST | ���󲻴��ڣ����ѯ�����˺š�TX�������
5  | ERRCODE_TX_TIMEOUT | TX ��ʱ��ָ�� TX �Ѿ�����ǰ�ڵ�� TX �������ȥ����==�������������һ�����ܱ�ִ��==
20  | ERRCODE_EXPR_CONDITION_RESULT_FALSE | ָ���ʽִ�н��Ϊ false����ζ�Ÿ� TX ��ǰû��ִ�гɹ���==���Ⲣ���������Ժ�����鲻�ܳɹ�==
21  | ERRCODE_EXPR_CONDITION_SYNTAX_ERROR | ָ���ʽ�﷨�������󣬴���� TX һ����ʧ��
90  | ERRCODE_INVALID_PUBKEY | ��Կ�Ƿ� 
91  | ERRCODE_INVALID_PRIKEY | ˽Կ�Ƿ�
92  | ERRCODE_ASSET_INVALID | �ʲ�issue ��ַ�Ƿ������� code ���Ȳ�����Ч��Χ��
93  | ERRCODE_INVALID_SIGNATURE | ǩ��Ȩ�ز������ﲻ������������ֵ
94  | ERRCODE_INVALID_ADDRESS | ��ַ�Ƿ�
95  | ERRCODE_TIME_NOT_IN_RANGE | ������Чʱ�䷶Χ��
96  | ERRCODE_NO_NETWORK_CONSENSUS | 
97  | ERRCODE_MISSING_OPERATIONS | TX ȷʵ����
98  | ERRCODE_LAGER_OPERATIONS | 
99  | ERRCODE_BAD_SEQUENCE | ���кŴ���
100 | ERRCODE_ACCOUNT_LOW_RESERVE | 
101 | ERRCODE_ACCOUNT_SOURCEDEST_EQUAL | ԴĿ���˺����
102 | ERRCODE_ACCOUNT_DEST_EXIST | �����˺Ų�����Ŀ���˺��Ѵ���
103 | ERRCODE_ACCOUNT_NOT_EXIST | �˻�������
104 | ERRCODE_ACCOUNT_ASSET_LOW_RESERVE | ֧���������ʲ�����
105 | ERRCODE_ACCOUNT_ASSET_AMOUNT_TOO_LARGE |
110 | ERRCODE_SEQNUMBER_NOT_MATCH | 
114 | ERRCODE_OUT_OF_TXCACHE |  TX �����������
120 | ERRCODE_WEIGHT_NOT_VALID | Ȩ��ֵ������Ч��Χ��
121 | ERRCODE_THRESHOLD_NOT_VALID | ����ֵ������Ч��Χ��
131 | ERRCODE_INPUT_NOT_EXIST |
144 | ERRCODE_INVALID_DATAVERSION | version �汾�Ų����˺�ƥ��
150 | ERRCODE_CONTRACT_EXISTS |
151 | ERRCODE_CONTRACT_EXECUTE_FAIL | ��Լִ��ʧ��
152 | ERRCODE_CONTRACT_SYNTAX_ERROR | ��Լ�﷨����ʧ��

## __������__

type | enum | ����˵��
|:--- | --- | --- |
1  | CREATE_ACCOUNT | �����˺�
2  | ISSUE_ASSET | �����ʲ�
3  | PAYMENT | ת���ʲ�
4  | SET_METADATA | ����metadata
5  | SET_SIGNER_WEIGHT | ����signerweight
6  | SET_THRESHOLD | ����threshold
7  | INVOKE_CONTRACT | ���ú�Լ