---
title: db_command (C++ COM 属性)
ms.date: 07/10/2018
f1_keywords:
- vc-attr.db_command
helpviewer_keywords:
- db_command attribute
ms.assetid: 714c3e15-85d7-408b-9a7c-88505c3e5d24
ms.openlocfilehash: 868ff862cc41543c8ebc7880a5d1a9a7e6b103f3
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2020
ms.locfileid: "90684587"
---
# <a name="db_command"></a>db_command

OLE DB コマンドを作成します。

## <a name="syntax"></a>構文

```cpp
[ db_command(command, name, source_name, hresult, bindings, bulk_fetch)
]
```

### <a name="parameters"></a>パラメーター

*command*<br/>
OLE DB コマンドのテキストを含むコマンド文字列。 簡単な例を次に示します。

```cpp
[ db_command ( command = "Select * from Products" ) ]
```

*command* の構文は次のとおりです。

> バインドパラメーターブロック 1 \
> &nbsp;&nbsp;OLE DB コマンド \
> バインドパラメーターブロック 2 \
> &nbsp;&nbsp;OLE DB コマンドの継続 \
> バインドパラメーターブロック 3 \
> ...

*binding parameter block* は次のように定義します。

> **( \[ ** *bindtype* **]** *szVar1* \[ 、 *szVar2* \[ 、 *nVar3* \[ 、...]] **)**

ここで、

- **(** は、データ バインディング ブロックの開始を示します。

- **\[***bindtype* **]** は、次の大文字と小文字を区別しない文字列のいずれかです。

  - ** \[ db_column]** は、各メンバー変数を行セットの列にバインドします。

  - ** \[ bindto]** ( ** \[ db_column]** と同じ)。

  - ** \[ in] は、** 入力パラメーターとしてメンバー変数をバインドします。

  - ** \[ out]** メンバー変数を出力パラメーターとしてバインドします。

  - ** \[ in、out] は、** 入力/出力パラメーターとしてメンバー変数をバインドします。

- *szvarx*、 *nvarx* は、現在のスコープ内のメンバー変数に解決されます。

- **)** は、データ バインディング ブロックの終了を示します。

コマンド文字列に \[ [in]、[out]、[in/out] などの指定子が1つ以上含まれている場合 \[ \[ 、 **db_command** はパラメーターマップを作成します。

コマンド文字列に db_column] や bindto などの1つ以上のパラメーターが含まれている場合 \[ \[ 、 **db_command** によって行セットとアクセサーマップが生成され、これらのバインドされた変数を処理できます。 詳しくは、「 [db_accessor](db-accessor.md) 」をご覧ください。

> [!NOTE]
> \[*bindtype*]クラスレベルで**db_command**を使用する場合、構文と*バインド*パラメーターは無効です。

バインディング パラメーター ブロックの例を次にいくつか示します。 次の例では、pubs データベースの authors テーブルの `m_au_fname` 列と `m_au_lname` 列に、それぞれ `au_fname` および `au_lname` データ メンバーをバインドします。

```cpp
TCHAR m_au_fname[21];
TCHAR m_au_lname[41];
TCHAR m_state[3] = 'CA';

[db_command (command = "SELECT au_fname([bindto]m_au_fname), au_lname([bindto]m_au_lname) " \
   "FROM dbo.authors " \
   "WHERE state = ?([in]m_state)")
]
```

*name*<br/>
Optional行セットを操作するために使用するハンドルの名前。 *name*を指定した場合、 **db_command** は指定された *name*のクラスを生成します。このクラスを使用して、行セットを走査したり、複数のアクション クエリを実行したりできます。 *name*を指定しないと、複数の結果行をユーザーに返すことはできません。

*source_name*<br/>
Optionalコマンドを実行するために `CSession` 属性が適用されているクラスの変数またはインスタンス `db_source` 。 「 [db_source](db-source.md)」をご覧ください。

**db_command** は *source_name* に使用されている変数が有効であることを確認するので、指定する変数は関数スコープまたはグローバル スコープに存在する必要があります。

*hresult*<br/>
Optionalこのデータベースコマンドの HRESULT を受け取る変数を指定します。 変数が存在しない場合は、属性によって自動的に挿入されます。

*現存*<br/>
OptionalOLE DB コマンドからバインドパラメーターを分離できます。

*バインディング*の値を指定した場合、 **db_command**は関連付けられている値を解析し、 \[ *bindtype*] パラメーターを解析しません。 これにより、OLE DB プロバイダーの構文を使用できます。 バインドパラメーターを使用せずに解析を無効にするには、を指定し `Bindings=""` ます。

*バインディング*の値を指定しなかった場合、 **db_command**はバインドパラメーターブロックを解析し、'**(**'、次に **\[** _bindtype_を角かっこで囲ん**で、** その後に1つ以上の以前に宣言された C++ メンバー変数、その後に '**)**' を検索します。 かっこで囲まれたすべてのテキストが最終的なコマンドから削除され、これらのパラメーターを使用してこのコマンドの列とパラメーターのバインディングが作成されます。

*bulk_fetch*<br/>
Optionalフェッチする行の数を指定する整数値。

既定値は 1 で、単一行のフェッチを指定します (行セットは [CRowset](../../data/oledb/crowset-class.md)型です)。

1 より大きい値は、バルク行フェッチを指定します。 バルク行フェッチとは、複数の行ハンドルをフェッチするバルク行セットの機能のことです (行セットは [CBulkRowset](../../data/oledb/cbulkrowset-class.md) 型であり、指定された行数で `SetRows` を呼び出します)。

*bulk_fetch* が 1 より小さい場合は、 `SetRows` は 0 を返します。

## <a name="remarks"></a>注釈

OLE DB コンシューマーは、**db_command** によって作成された [CCommand](../../data/oledb/ccommand-class.md) オブジェクトを使用して、コマンドを実行します。

**db_command** はクラス スコープまたは関数スコープで使用できます。主な違いは、 `CCommand` オブジェクトのスコープです。 関数スコープでは、バインディングなどのデータは関数の終了時に終了します。 クラスと関数スコープの両方の使用には OLE DB コンシューマーテンプレートクラスが含まれ `CCommand<>` ますが、関数とクラスのケースではテンプレート引数が異なります。 関数の場合、バインドはローカル変数で構成されるに対して行われますが、 `Accessor` クラスの使用法では、 `CAccessor` 派生クラスが引数として推論されます。 クラス属性として使用すると、 **db_command** は **db_column**と共に動作します。

**db_command** を使用して、結果セットを返さないコマンドを実行できます。

コンシューマー属性プロバイダーがこの属性をクラスに適用すると、コンパイラはクラスの名前を \_ *classname*アクセサーに変更します。ここで、 *classname*はクラスに指定した名前になります。また、コンパイラは*classname と*いうクラスを作成します。これは classname アクセサーから派生し \_ *YourClassName*ます。  クラス ビューでは、両方のクラスが表示されます。

## <a name="examples"></a>例

この例では、テーブルから state 列が 'CA' と一致する姓と名を選択するコマンドを定義しています。 **db_command** は、ウィザードで生成される [OpenAll and CloseAll](../../data/oledb/consumer-wizard-generated-methods.md)などの関数および `CRowset` MoveNext [などの](../../data/oledb/crowset-movenext.md)メンバー関数を呼び出すことができる行セットを作成して読み取ります。

このコードでは、pubs データベースに接続する独自の接続文字列を指定する必要があることに注意してください。 開発環境でこれを行う方法については、「 [方法: データベースに接続して既存のオブジェクトを参照](/sql/ssdt/how-to-connect-to-a-database-and-browse-existing-objects) し、 [新しい接続を追加](/visualstudio/data-tools/add-new-connections)する」を参照してください。

```cpp
// db_command.h
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>

#pragma once

[  db_source(L"your connection string"), db_command(L" \
      SELECT au_lname, au_fname \
      FROM dbo.authors \
      WHERE state = 'CA'")  ]

struct CAuthors {
   // In order to fix several issues with some providers, the code below may bind
   // columns in a different order than reported by the provider

   DBSTATUS m_dwau_lnameStatus;
   DBSTATUS m_dwau_fnameStatus;
   DBLENGTH m_dwau_lnameLength;
   DBLENGTH m_dwau_fnameLength;

   [ db_column("au_lname", status="m_dwau_lnameStatus", length="m_dwau_lnameLength") ] TCHAR m_au_lname[41];
   [ db_column("au_fname", status="m_dwau_fnameStatus", length="m_dwau_fnameLength") ] TCHAR m_au_fname[21];

   [ db_param("7", paramtype="DBPARAMIO_INPUT") ] TCHAR m_state[3];

   void GetRowsetProperties(CDBPropSet* pPropSet) {
      pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
      pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
   }
};
```

```cpp
// db_command.cpp
// compile with: /c
#include "db_command.h"

int main(int argc, _TCHAR* argv[]) {
   HRESULT hr = CoInitialize(NULL);

   // Instantiate rowset
   CAuthors rs;

   // Open rowset and move to first row
   strcpy_s(rs.m_state, sizeof(rs.m_state), _T("CA"));
   hr = rs.OpenAll();
   hr = rs.MoveFirst();

   // Iterate through the rowset
   while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET ) {
      // Print out the column information for each row
      printf("First Name: %s, Last Name: %s\n", rs.m_au_fname, rs.m_au_lname);
      hr = rs.MoveNext();
   }

   rs.CloseAll();
   CoUninitialize();
}
```

この例では、データ ソース クラス `db_source` で `CMySource`を使用し、コマンド クラス `db_command` と `CCommand1` で `CCommand2`を使用します。

```cpp
// db_command_2.cpp
// compile with: /c
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>
// class usage for both db_source and db_command

[  db_source(L"your connection string"), db_command(L" \
      SELECT au_lname, au_fname \
      FROM dbo.authors \
      WHERE state = 'CA'")  ]
struct CMySource {
   HRESULT OpenDataSource() {
      return S_OK;
   }
};

[db_command(command = "SELECT * FROM Products")]
class CCommand1 {};

[db_command(command = "SELECT FNAME, LNAME FROM Customers")]
class CCommand2 {};

int main() {
   CMySource s;
   HRESULT hr = s.OpenDataSource();
   if (SUCCEEDED(hr)) {
      CCommand1 c1;
      hr = c1.Open(s);

      CCommand2 c2;
      hr = c2.Open(s);
   }

   s.CloseDataSource();
}
```

## <a name="requirements"></a>必要条件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|**`class`**、 **`struct`** 、member、method、local|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[OLE DB のコンシューマー属性](ole-db-consumer-attributes.md)<br/>
[スタンドアロン属性](stand-alone-attributes.md)
