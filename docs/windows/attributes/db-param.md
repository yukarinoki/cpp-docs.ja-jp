---
description: '詳細については、次を参照してください: db_param'
title: db_param (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.db_param
helpviewer_keywords:
- db_param attribute
ms.assetid: a28315f5-4722-459e-92ef-32e83c0b205a
ms.openlocfilehash: 27666b4cdf027e24b54326a3acc5fe701b9f6f44
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333106"
---
# <a name="db_param"></a>db_param

指定されたメンバー変数を入力パラメーターまたは出力パラメーターに関連付けて、その変数を区切ります。

## <a name="syntax"></a>構文

```cpp
[ db_param(ordinal, paramtype="DBPARAMIO_INPUT", dbtype, precision, scale, status, length) ]
```

### <a name="parameters"></a>パラメーター

*数値*<br/>
データをバインドする行セット内のフィールドに対応する列番号 (DBCOLUMNINFO ordinal)。

*が paramtype*<br/>
Optionalパラメーターに設定する型。 プロバイダーは、基になるデータソースでサポートされているパラメーター i/o 型のみをサポートしています。 この型は、1つ以上の DBPARAMIOENUM 値を組み合わせたものです。

- DBPARAMIO_INPUT 入力パラメーター。

- DBPARAMIO_OUTPUT 出力パラメーター。

- DBPARAMIO_NOTPARAM アクセサーにパラメーターがありません。 `eParamIO`行アクセサーでこの値をに設定すると、パラメーターが無視されることがユーザーに通知されます。

*dbtype*<br/>
Optional列エントリの OLE DB [型インジケーター](/previous-versions/windows/desktop/ms711251(v=vs.85)) 。

*有効桁数 (precision)*<br/>
Optional列エントリに使用される有効桁数。 詳細については、 `bPrecision` [DBBINDING 構造体](/previous-versions/windows/desktop/ms716845(v=vs.85))の要素の説明を参照してください。

*scale*<br/>
Optional列エントリに使用される小数点以下桁数です。 詳細については、 `bScale` [DBBINDING 構造体](/previous-versions/windows/desktop/ms716845(v=vs.85))の要素の説明を参照してください。

*status*<br/>
Optionalこの列の状態を保持するために使用されるメンバー変数。 状態は、列の値がデータ値か、NULL などの他の値であるかを示します。 使用可能な値については、 *OLE DB プログラマーリファレンス* の「 [Status](/previous-versions/windows/desktop/ms722617(v=vs.85)) 」を参照してください。

*length*<br/>
Optional列のサイズを保持するために使用されるメンバー変数 (バイト単位)。

## <a name="remarks"></a>解説

**db_param** は、コマンドで使用するパラメーターを定義します。したがって、と共に使用し `db_command` ます。 たとえば、 **db_param** を使用して、SQL クエリまたはストアドプロシージャでパラメーターをバインドできます。 ストアドプロシージャのパラメーターは疑問符 (?) で示されます。また、パラメーターが表示される順序でデータメンバーをバインドする必要があります。

OLE DB ベースのバインドに参加できるメンバーデータを区切る **db_param** `ICommandWithParameters` ます。 パラメーターの型 (入力または出力)、OLE DB 型、有効桁数、小数点以下桁数、状態、および長さを指定したパラメーターに設定します。 この属性は OLE DB コンシューマーマクロ BEGIN_PARAM_MAP を挿入します...END_PARAM_MAP。 **Db_param** 属性でマークした各メンバーは、マップ内の1つのエントリを COLUMN_ENTRY の形式で使用します。

**db_param** は、 [db_table](db-table.md) 属性または [db_command](db-command.md) 属性と組み合わせて使用されます。

コンシューマー属性プロバイダーがこの属性をクラスに適用すると、コンパイラはクラスの名前を \_ *classname* アクセサーに変更します。ここで、 *classname* はクラスに指定した名前になります。また、コンパイラは *classname と* いうクラスを作成します。これは classname アクセサーから派生し \_ ます。  クラス ビューでは、両方のクラスが表示されます。

## <a name="example"></a>例

次の例では、Northwind データベースの SalesbyYear ストアドプロシージャに基づいてコマンドクラスを作成します。 ストアドプロシージャの最初のパラメーターを変数に関連付け、 `m_RETURN_VALUE` それを出力パラメーターとして定義します。 最後の2つの (入力) パラメーターを `m_Beginning_Date` とに関連付け `m_Ending_Date` ます。

次の例では、 `nOutput` 変数と出力パラメーターを関連付けます。

```cpp
// db_param.cpp
// compile with: /LD
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>

[ db_source(L"my_connection_string"),
  db_command(L"{ ? = CALL dbo.\"Sales by Year\"(?,?) }")
]
struct CSalesbyYear {
   DBSTATUS m_dwShippedDateStatus;
   DBSTATUS m_dwOrderIDStatus;
   DBSTATUS m_dwSubtotalStatus;
   DBSTATUS m_dwYearStatus;

   DBLENGTH m_dwShippedDateLength;
   DBLENGTH m_dwOrderIDLength;
   DBLENGTH m_dwSubtotalLength;
   DBLENGTH m_dwYearLength;

   // Bind columns
   [ db_column("1", status="m_dwShippedDateStatus", length="m_dwShippedDateLength") ] DBTIMESTAMP m_ShippedDate;
   [ db_column("2", status="m_dwOrderIDStatus", length="m_dwOrderIDLength") ] LONG m_OrderID;
   [ db_column("3", status="m_dwSubtotalStatus", length="m_dwSubtotalLength") ] CURRENCY m_Subtotal;
   [ db_column("4", status="m_dwYearStatus", length="m_dwYearLength") ] TCHAR m_Year[31];

   // Bind parameters
   [ db_param("1", paramtype="DBPARAMIO_OUTPUT") ] LONG m_RETURN_VALUE;
   [ db_param("2", paramtype="DBPARAMIO_INPUT") ] DBTIMESTAMP m_Beginning_Date;
   [ db_param("3", paramtype="DBPARAMIO_INPUT") ] DBTIMESTAMP m_Ending_Date;
};
```

## <a name="requirements"></a>要件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|**`class`**、 **`struct`** 、member、method、local|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[OLE DB のコンシューマー属性](ole-db-consumer-attributes.md)
