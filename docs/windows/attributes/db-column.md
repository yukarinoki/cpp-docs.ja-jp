---
title: db_column (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.db_column
helpviewer_keywords:
- db_column attribute
ms.assetid: 58da4afc-f69c-4ae6-af9a-3f9515f56081
ms.openlocfilehash: 98f546a243016fa85f6d71159ab2fc0a7963bae3
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833116"
---
# <a name="db_column"></a>db_column

指定された列を行セット内の変数にバインドします。

## <a name="syntax"></a>構文

```cpp
[ db_column(ordinal, dbtype, precision, scale, status, length) ]
```

### <a name="parameters"></a>パラメーター

*数値*<br/>
`DBCOLUMNINFO`データをバインドする行セット内のフィールドに対応する序数列番号 (序数) または列名 (ANSI または Unicode 文字列)。 数値を使用する場合は、連続する序数 (例: 1、2、3、5) をスキップできます。 使用する OLE DB プロバイダーでサポートされている場合は、名前にスペースを含めることができます。 たとえば、次のいずれかの形式を使用できます。

```cpp
[db_column("2")] TCHAR szCity[30];
[db_column(L"city_name")] TCHAR szCity[30];
```

*dbtype*<br/>
Optional列エントリの OLE DB [型インジケーター](/previous-versions/windows/desktop/ms711251(v=vs.85)) 。

*有効桁数 (precision)*<br/>
Optional列エントリに使用される有効桁数。 詳細については、 `bPrecision` [DBBINDING 構造体](/previous-versions/windows/desktop/ms716845(v=vs.85))の要素の説明を参照してください。

*scale*<br/>
Optional列エントリに使用される小数点以下桁数です。 詳細については、 `bScale` [DBBINDING 構造体](/previous-versions/windows/desktop/ms716845(v=vs.85))の要素の説明を参照してください。

*status*<br/>
Optionalこの列の状態を保持するために使用されるメンバー変数。 状態は、列の値がデータ値か、NULL などの他の値であるかを示します。 使用可能な値については、 *OLE DB プログラマーリファレンス*の「 [Status](/previous-versions/windows/desktop/ms722617(v=vs.85)) 」を参照してください。

*length*<br/>
Optional列のサイズを保持するために使用されるメンバー変数 (バイト単位)。

## <a name="remarks"></a>解説

**db_column** は、指定されたテーブル列を行セット内の変数にバインドします。 OLE DB ベースのバインドに参加できるメンバーデータを区切り `IAccessor` ます。 この属性は、OLE DB コンシューマーマクロ [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)、 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)、および [COLUMN_ENTRY](../../data/oledb/column-entry.md)を使用して通常定義される列マップを設定します。 これらは、OLE DB [DBBINDING 構造体](/previous-versions/windows/desktop/ms716845(v=vs.85)) を操作して、指定された列をバインドします。 **Db_column**属性でマークする各メンバーは、列エントリの形式で列マップ内の1つのエントリを使用します。 したがって、この属性は、コマンドまたはテーブルクラスに列マップを配置するときに使用します。

**Db_column**は、 [db_table](db-table.md)または[db_command](db-command.md)の属性と組み合わせて使用します。

コンシューマー属性プロバイダーがこの属性をクラスに適用すると、コンパイラはクラスの名前を \_ *classname*アクセサーに変更します。ここで、 *classname*はクラスに指定した名前になります。また、コンパイラは*classname と*いうクラスを作成します。これは classname アクセサーから派生し \_ *YourClassName*ます。  クラス ビューでは、両方のクラスが表示されます。

アプリケーションで使用されるこの属性の例については、「 [MultiRead](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Consumer)」を参照してください。

## <a name="example"></a>例

このサンプルでは、テーブル内の列を **`long`** データメンバーにバインドし、[状態] フィールドと [長さ] フィールドを指定します。

```cpp
// db_column_1.cpp
// compile with: /LD
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>

[ db_command(L"Select * from Products") ]
class CProducts {
   DBSTATUS m_dwProductIDStatus;
   DBLENGTH m_dwProductIDLength;

   [ db_column("1", status="m_dwProductIDStatus", length="m_dwProductIDLength") ] LONG m_ProductID;
};
```

## <a name="example"></a>例

このサンプルでは、4つの列を **`long`** 、文字列、タイムスタンプ、および `DB_NUMERIC` 整数の順序でバインドします。

```cpp
// db_column_2.cpp
// compile with: /LD
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>

[ db_command(L"Select * from Products") ]
class CProducts {
   [db_column("1")] LONG m_OrderID;
   [db_column("2")] TCHAR m_CustomerID[6];
   [db_column("4")] DB_NUMERIC m_OrderDate;
   [db_column("7", dbtype="DBTYPE_NUMERIC")] DB_NUMERIC m_ShipVia;
};
```

## <a name="requirements"></a>必要条件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|**`class`**、 **`struct`** 、member、メソッド|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[OLE DB のコンシューマー属性](ole-db-consumer-attributes.md)<br/>
[クラス属性](class-attributes.md)
