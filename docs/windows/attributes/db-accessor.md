---
title: db_accessor (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.db_accessor
helpviewer_keywords:
- db_accessor attribute
ms.assetid: ec407a9f-24d7-4822-96d4-7cc6a0301815
ms.openlocfilehash: 559838201e3d1c425b6b1bf7f3650d9635c44c97
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833141"
---
# <a name="db_accessor"></a>db_accessor

`db_column`ベースのバインドに参加する属性をグループ化 `IAccessor` します。

## <a name="syntax"></a>構文

```cpp
[ db_accessor(num, auto) ]
```

#### <a name="parameters"></a>パラメーター

*num*<br/>
アクセサー番号 (0 から始まる整数のインデックス) を指定します。 アクセサー番号は、整数または定義済みの値を使用して、昇順で指定する必要があります。

*auto*<br/>
アクセサーが自動的に取得されるか (TRUE)、取得されないか (FALSE) を指定するブール値。

## <a name="remarks"></a>解説

**db_accessor** `db_column` `db_param` は、同じクラスまたは関数内の後続のおよび属性の基になる OLE DB アクセサーを定義します。 **db_accessor** はメンバーレベルで使用 `db_column` でき、OLE DB ベースのバインドに参加する属性をグループ化するために使用され `IAccessor` ます。 または属性と組み合わせて使用さ `db_table` れ `db_command` ます。 この属性を呼び出すことは、マクロの [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) と [END_ACCESSOR](../../data/oledb/end-accessor.md) の呼び出しに似ています。

**db_accessor** は、行セットを生成し、それを対応するアクセサーマップにバインドします。 **Db_accessor**を呼び出さないと、アクセサー0が自動的に生成され、すべての列のバインドがこのアクセサーブロックにマップされます。

**db_accessor** 、データベースの列バインドを1つ以上のアクセサーにグループ化します。 複数のアクセサーを使用する必要があるシナリオの詳細については、「 [行セットでの複数のアクセサーの使用](../../data/oledb/using-multiple-accessors-on-a-rowset.md)」を参照してください。 「 [ユーザーレコード](../../data/oledb/user-records.md)」の「複数のアクセサーのユーザーレコードのサポート」も参照してください。

コンシューマー属性プロバイダーがこの属性をクラスに適用すると、コンパイラはクラスの名前を \_ *classname*アクセサーに変更します。ここで、 *classname*はクラスに指定した名前になります。また、コンパイラは*classname と*いうクラスを作成します。これは classname アクセサーから派生し \_ *YourClassName*ます。  クラス ビューでは、両方のクラスが表示されます。

## <a name="example"></a>例

次の例では、 **db_accessor** を使用して、Orders テーブルの列を Northwind データベースから2つのアクセサーにグループ化します。 アクセサー0は自動アクセサーであり、アクセサー1はではありません。

```cpp
// cpp_attr_ref_db_accessor.cpp
// compile with: /LD /link /OPT:NOREF
#define _ATL_ATTRIBUTES
#include <atlbase.h>
#include <atldbcli.h>

[ db_command(L"SELECT LastName, FirstName FROM Orders") ]
class CEmployees {
public:
   [ db_accessor(0, TRUE) ];
   [ db_column("1") ] LONG m_OrderID;
   [ db_column("2") ] TCHAR m_CustomerID[6];
   [ db_column("4") ] DBTIMESTAMP m_OrderDate;

   [ db_accessor(1, FALSE) ];
   [ db_column("8") ] CURRENCY m_Freight;
};
```

## <a name="requirements"></a>必要条件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|属性ブロック|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[OLE DB のコンシューマー属性](ole-db-consumer-attributes.md)
