---
title: db_table (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.db_table
helpviewer_keywords:
- db_table attribute
ms.assetid: ff9eb957-4e6d-4175-afcc-fd8ea916cec0
ms.openlocfilehash: 9e05a980764b8b97f6c774165fdddd5428a0c989
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215284"
---
# <a name="db_table"></a>db_table

OLE DB テーブルを開きます。

## <a name="syntax"></a>構文

```cpp
[ db_table(db_table, name, source_name, hresult) ]
```

### <a name="parameters"></a>パラメーター

*db_table*<br/>
データベーステーブルの名前を指定する文字列 ("Products" など)。

*name*<br/>
Optionalテーブルを操作するために使用するハンドルの名前。 複数の結果行を返す場合は、このパラメーターを指定する必要があります。 **db_table**は、指定された*名前*を持つ変数を生成します。この変数は、行セットを走査したり、複数のアクションクエリを実行したりするために使用できます。

*source_name*<br/>
Optionalコマンドを実行するために `CSession` 属性が適用されているクラスの変数またはインスタンス `db_source` 。 「 [db_source](db-source.md)」をご覧ください。

*hresult*<br/>
Optionalこのデータベースコマンドの HRESULT を受け取る変数を指定します。 変数が存在しない場合は、属性によって自動的に挿入されます。

## <a name="remarks"></a>解説

**db_table**は、テーブルを開くために OLE DB コンシューマーによって使用される[CTable](../../data/oledb/ctable-class.md)オブジェクトを作成します。 この属性はクラスレベルでのみ使用できます。インラインで使用することはできません。 を使用し `db_column` てテーブル列を変数にバインドします。 `db_param` パラメーターの区切り記号 (パラメーターの型の設定など) を使用します。

コンシューマー属性プロバイダーがこの属性をクラスに適用すると、コンパイラはクラスの名前を \_ *classname*アクセサーに変更します。ここで、 *classname*はクラスに指定した名前になります。また、コンパイラは*classname と*いうクラスを作成します。これは classname アクセサーから派生し \_ *YourClassName*ます。  クラス ビューでは、両方のクラスが表示されます。

## <a name="example"></a>例

次の例では、で使用する Products テーブルを開き `CProducts` ます。

```cpp
// db_table.cpp
// compile with: /LD
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>

[ db_table(L"dbo.Products") ]
class CProducts {
   [ db_column("1") ] LONG m_ProductID;
};
```

アプリケーションで使用されるこの属性の例については、「 [MultiRead](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Consumer)」を参照してください。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**適用対象**|**`class`**, **`struct`**|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[OLE DB のコンシューマー属性](ole-db-consumer-attributes.md)
