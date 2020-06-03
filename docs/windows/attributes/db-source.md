---
title: db_source (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.db_source
helpviewer_keywords:
- db_source attribute
ms.assetid: 0ec8bbf7-ade2-4899-bf4c-8608b92779bc
ms.openlocfilehash: 6346a8d6f60313dc17bbcbad062aa888857f0b67
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167278"
---
# <a name="db_source"></a>db_source

データソースへの接続を作成します。

## <a name="syntax"></a>構文

```cpp
[ db_source(db_source, name, hresult) ]
```

### <a name="parameters"></a>パラメーター

*db_source*<br/>
データソースへの接続に使用される接続文字列。 接続文字列の形式については、「Microsoft Data Access Components (MDAC) SDK の[接続文字列とデータリンク](/previous-versions/windows/desktop/ms718376(v=vs.85))」を参照してください。

*name*<br/>
Optionalクラスで**db_source**を使用する場合、 *name*は、 **db_source**属性が適用されているデータソースオブジェクトのインスタンスです (例1を参照)。 メソッドの実装でインライン**db_source**を使用する場合、 *name*はデータソースへのアクセスに使用できる変数 (メソッドのローカル) です (例2を参照)。 この*名前*を `db_command` の*source_name*パラメーターに渡して、データソースとコマンドを関連付けます。

*hresult*<br/>
Optionalこのデータベースコマンドの HRESULT を受け取る変数を指定します。 変数が存在しない場合は、属性によって自動的に挿入されます。

## <a name="remarks"></a>解説

**db_source**によって、OLE DB のコンシューマーデータソースとの接続を表す[CDataSource](../../data/oledb/cdatasource-class.md)オブジェクトと[CSession](../../data/oledb/csession-class.md)オブジェクトが作成されます。

クラスで**db_source**を使用すると、`CSession` オブジェクトはクラスのメンバーになります。

メソッドで**db_source**を使用すると、挿入されたコードがメソッドスコープ内で実行され、`CSession` オブジェクトがローカル変数として作成されます。

**db_source** 、クラスまたはメソッド内にデータソースプロパティを追加します。 これは `db_command` と組み合わせて使用されます ( *db_source* *name*パラメーターを*source_name*パラメーターとして受け取ります)。

コンシューマー属性プロバイダーがこの属性をクラスに適用すると、コンパイラはクラスの名前を*classname*アクセサーに \_します。ここで、 *classname*はクラスに指定した名前になります。また、コンパイラは classname というクラスも作成します。これ*は、\_* *classname*アクセサーから派生します。  クラス ビューでは、両方のクラスが表示されます。

アプリケーションで使用されるこの属性の例については、「 [MultiRead](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Consumer)」を参照してください。

## <a name="example"></a>例

このサンプルでは、クラスの**db_source**を呼び出して、Northwind データベースを使用して `ds` データソースへの接続を作成します。 `ds` は、データソースのハンドルであり、`CMyCommand` クラスに内部的に使用できます。

```cpp
// db_source_1.cpp
// compile with: /LD
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>

[
  db_source(L"my_connection_string", name="ds"),
  db_command(L"select * from Products")
]
class CMyCommand {};
```

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**class**、 **struct**、member、method、local|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>参照

[OLE DB コンシューマー属性](ole-db-consumer-attributes.md)
