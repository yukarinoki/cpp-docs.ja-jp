---
description: '詳細情報: テクニカルノート 43: RFX ルーチン'
title: 'テクニカル ノート 43: RFX ルーチン'
ms.date: 06/28/2018
f1_keywords:
- RFX
helpviewer_keywords:
- RFX (record field exchange), architecture
- TN043
- RFX (record field exchange)
ms.assetid: f552d0c1-2c83-4389-b472-42c9940aa713
ms.openlocfilehash: 6e5ac8271739e5cab80b79cb915b07e7d25622cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215223"
---
# <a name="tn043-rfx-routines"></a>テクニカル ノート 43: RFX ルーチン

> [!NOTE]
> 次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。

このメモでは、レコードフィールドエクスチェンジ (RFX) アーキテクチャについて説明します。 また、 **RFX_** プロシージャを記述する方法についても説明します。

## <a name="overview-of-record-field-exchange"></a>レコードフィールドエクスチェンジの概要

すべてのレコードセットフィールド関数は、C++ コードで実行されます。 特別なリソースやマジックマクロはありません。 このメカニズムの中核となるのは、すべての派生レコードセットクラスでオーバーライドする必要がある仮想関数です。 次の形式で常に検出されます。

```cpp
void CMySet::DoFieldExchange(CFieldExchange* pFX)
{
    //{{AFX_FIELD_MAP(CMySet)
        <recordset exchange field type call>
        <recordset exchange function call>
    //}}AFX_FIELD_MAP
}
```

特別な形式の AFX コメントを使用すると、ClassWizard はこの関数内のコードを検索して編集できます。 ClassWizard と互換性のないコードは、特別な形式のコメントの外部に配置する必要があります。

上の例で \<recordset_exchange_field_type_call> は、は次の形式になっています。

```cpp
pFX->SetFieldType(CFieldExchange::outputColumn);
```

との \<recordset_exchange_function_call> 形式は次のとおりです。

```cpp
RFX_Custom(pFX, "Col2", m_Col2);
```

ほとんどの **RFX_** 関数には上記の3つの引数がありますが、一部 (やなど) には `RFX_Text` 追加の `RFX_Binary` 省略可能な引数があります。

各関数に複数の **RFX_** を含めることができ `DoDataExchange` ます。

MFC に用意されているすべてのレコードセットフィールド交換ルーチンの一覧については、「afxdb.h」を参照してください。

レコードセットフィールド呼び出しは、クラスのフィールドデータを格納するためのメモリ位置 (通常はデータメンバー) を登録する方法です `CMySet` 。

## <a name="notes"></a>メモ

レコードセットフィールド関数は、クラスでのみ動作するように設計されてい `CRecordset` ます。 これらは、他の MFC クラスでは一般に使用できません。

データの初期値は、標準 C++ コンストラクターで設定されます。通常は、とのコメントが含まれるブロックに `//{{AFX_FIELD_INIT(CMylSet)` `//}}AFX_FIELD_INIT` あります。

各 **RFX_** 関数は、フィールドを編集するための準備として、フィールドのダーティステータスを返すからフィールドをアーカイブするなど、さまざまな操作をサポートする必要があります。

(たとえば、) を呼び出す各関数は、の `DoFieldExchange` `SetFieldNull` 呼び出しを `IsFieldDirty` 囲む独自の初期化を行い `DoFieldExchange` ます。

## <a name="how-does-it-work"></a>動作のしくみ

レコードフィールドエクスチェンジを使用するには、次のことを理解する必要はありません。 ただし、これがバックグラウンドでどのように動作するかを理解することは、独自の exchange プロシージャを作成するのに役立ちます。

`DoFieldExchange`メンバー関数は、メンバー関数とよく似てい `Serialize` ます。これは、外部フォーム (この場合は、ODBC クエリの結果の列) からクラスのメンバーデータへのデータの取得または設定を行います。 *PFX* パラメーターはデータ交換を実行するためのコンテキストであり、の *CArchive* パラメーターに似てい `CObject::Serialize` ます。 *PFX* ( `CFieldExchange` オブジェクト) の操作インジケーターは、に似ていますが、 *CArchive* 方向フラグの一般化です。 RFX 関数は、次の操作をサポートする必要がある場合があります。

- `BindParam` — ODBC がパラメーターデータを取得する場所を示します。

- `BindFieldToColumn` — ODBC が outputColumn データを取得/デポジットする必要があることを示します。

- `Fixup` — `CString/CByteArray` 長さの設定、NULL ステータスビットの設定

- `MarkForAddNew` — AddNew 呼び出し以降に値が変更された場合はダーティとしてマークします

- `MarkForUpdate` —エディット呼び出し以降に値が変更された場合はダーティとしてマークします

- `Name` —ダーティとマークされたフィールドのフィールド名を追加します。

- `NameValue` —ダーティとマークされた \<column name> フィールドに "=" を追加します。

- `Value` — "" の後に区切り記号 (', '、' ' など) を追加します。

- `SetFieldDirty` —ステータスビットダーティ (つまり、変更された) フィールドを設定します。

- `SetFieldNull` —フィールドの null 値を示すステータスビットを設定します。

- `IsFieldDirty` -ダーティステータスビットの戻り値

- `IsFieldNull` — Null ステータスビットの戻り値

- `IsFieldNullable` -フィールドが NULL 値を保持できる場合に TRUE を返します。

- `StoreField` —アーカイブフィールド値

- `LoadField` —アーカイブされたフィールド値の再読み込み

- `GetFieldInfoValue` —フィールドに関する一般的な情報を返します。

- `GetFieldInfoOrdinal` —フィールドに関する一般的な情報を返します。

## <a name="user-extensions"></a>ユーザー拡張機能

既定の RFX 機構を拡張するには、いくつかの方法があります。 そのための方法は次のとおりです。

- 新しいデータ型を追加します。 次に例を示します。

    ```cpp
    CBookmark
    ```

- 新しい exchange プロシージャを追加します (RFX_)。

    ```cpp
    void AFXAPI RFX_Bigint(CFieldExchange* pFX,
        const char *szName,
        BIGINT& value);
    ```

- `DoFieldExchange`メンバー関数には、追加の RFX 呼び出しまたはその他の有効な C++ ステートメントが条件付きで含まれている必要があります。

    ```cpp
    while (posExtraFields != NULL)
    {
        RFX_Text(pFX,
        m_listName.GetNext(posExtraFields),
        m_listValue.GetNext(posExtraValues));
    }
    ```

> [!NOTE]
> このようなコードは、ClassWizard で編集することはできません。また、特殊な書式のコメント以外でのみ使用してください。

## <a name="writing-a-custom-rfx"></a>カスタム RFX の記述

独自のカスタム RFX 関数を作成するには、既存の RFX 関数をコピーして、独自の目的に変更することをお勧めします。 コピーする適切な RFX を選択すると、ジョブをより簡単に行うことができます。 一部の RFX 関数には、コピーする対象を決定する際に考慮する必要がある固有のプロパティがいくつかあります。

`RFX_Long` および `RFX_Int` : これらは、最も単純な RFX 関数です。 データ値は特別な解釈を必要とせず、データサイズが固定されています。

`RFX_Single` また、 `RFX_Double` 上記の RFX_Long と RFX_Int と同様に、これらの関数は単純であり、既定の実装を広範囲に利用できます。 ただし、これらは、明示的に参照されている場合にのみランタイム浮動小数点ライブラリの読み込みを有効にするために、dbrfx ではなく dbflt に格納されます。

`RFX_Text` および `RFX_Binary` : これら2つの関数は、文字列/バイナリ情報を保持するために静的バッファーを事前に確保し、&値を登録するのではなく、これらのバッファーを ODBC SQLBindCol に登録する必要があります。 このため、この2つの関数には特殊なケースコードが多数あります。

`RFX_Date`: ODBC では、日付と時刻の情報が独自の TIMESTAMP_STRUCT データ構造で返されます。 この関数は、日付と時刻のデータを送信および受信するための "プロキシ" として、TIMESTAMP_STRUCT を動的に割り当てます。 さまざまな操作で、C++ オブジェクトと TIMESTAMP_STRUCT プロキシ間で日付と時刻の情報を転送する必要があり `CTime` ます。 これにより、この関数はかなり複雑になりますが、データ転送にプロキシを使用する方法の例としては、この機能が非常に複雑になります。

`RFX_LongBinary`: これは、データの送受信に列バインドを使用しない唯一のクラスライブラリ RFX 関数です。 この関数は、BindFieldToColumn 操作を無視し、その代わりに、フィックスアップ操作中に、受信 SQL_LONGVARCHAR または SQL_LONGVARBINARY データを保持するストレージを割り当て、次に SQLGetData 呼び出しを実行して、割り当てられたストレージに値を取得します。 データソースへのデータ値の送信を準備するとき (NameValue や値の操作など)、この関数は ODBC の DATA_AT_EXEC 機能を使用します。 SQL_LONGVARBINARY と SQL_LONGVARCHARs の使用方法の詳細については、「 [テクニカルノート 45](../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md) 」を参照してください。

独自の **RFX_** 関数を記述する場合は、を使用して特定の操作を実装できることがよくあり `CFieldExchange::Default` ます。 対象の操作の既定の実装を確認します。 操作を実行する場合は、 **RFX_** 関数に記述する場合は、に委任でき `CFieldExchange::Default` ます。 の呼び出しの例については、dbrfx を参照してください `CFieldExchange::Default` 。

`IsFieldType`RFX 関数の先頭でを呼び出し、FALSE が返された場合は、すぐにを返すことが重要です。 このメカニズムにより、パラメーター操作が *Outputcolumns* に対して実行されるのを防ぐことが `BindParam` できます ( *outputcolumns* でを呼び出すなど)。 さらに、は、 `IsFieldType` *outputcolumns* (*m_nFields*) および params (*m_nParams*) のカウントを自動的に追跡します。

## <a name="see-also"></a>関連項目

[番号別テクニカルノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカルノート](../mfc/technical-notes-by-category.md)
