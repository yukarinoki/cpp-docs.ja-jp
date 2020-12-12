---
description: '詳細については、次を参照してください: テクニカルノート 45: MFC/データベースの Long Varchar/Varbinary のサポート'
title: 'テクニカルノート 45: MFC-Database 長い Varchar-Varbinary のサポート'
ms.date: 11/04/2016
helpviewer_keywords:
- TN045
- Varbinary data type
- Varchar data type
ms.assetid: cf572c35-5275-45b5-83df-5f0e36114f40
ms.openlocfilehash: 4e19147ab5ca392307f331b12d3cf24eb5fcc06f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215184"
---
# <a name="tn045-mfcdatabase-support-for-long-varcharvarbinary"></a>テクニカル ノート 45: MFC/データベースの Long Varchar/Varbinary 型のサポート

> [!NOTE]
> 次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。

このメモでは、MFC データベースクラスを使用して、ODBC **SQL_LONGVARCHAR** および **SQL_LONGVARBINARY** データ型を取得して送信する方法について説明します。

## <a name="overview-of-long-varcharvarbinary-support"></a>Long Varchar/Varbinary サポートの概要

ODBC **SQL_LONG_VARCHAR** および **SQL_LONGBINARY** データ型 (長いデータ列と呼ばれます) では、大量のデータを保持できます。 このデータを処理するには、次の3つの方法があります。

- これをにバインド `CString` / `CByteArray` します。

- これをにバインド `CLongBinary` します。

- データベースクラスに関係なく、すべてをバインドして、長いデータ値を手動で取得して送信することは避けてください。

これら3つの方法にはそれぞれ長所と短所があります。

長いデータ列は、クエリのパラメーターではサポートされていません。 これらは outputColumns でのみサポートされています。

## <a name="binding-a-long-data-column-to-a-cstringcbytearray"></a>Long データ列を CString/CByteArray にバインドする

利点:

この方法はわかりやすく、使い慣れたクラスを使用して作業します。 フレームワークは、を `CFormView` 使用したのサポートを提供 `CString` `DDX_Text` します。 クラスとクラスを使用した一般的な文字列またはコレクションの機能が多数あり、 `CString` `CByteArray` データ値を保持するためにローカルに割り当てられるメモリの量を制御できます。 フレームワークでは、または関数の呼び出し中にフィールドデータの古いコピーが保持され、 `Edit` `AddNew` データに対する変更はフレームワークによって自動的に検出されます。

> [!NOTE]
> は文字データを操作するように設計されているため、バイナリデータを操作するためには、 `CString` `CByteArray` 文字データ (**SQL_LONGVARCHAR**) をに `CString` 、バイナリデータ (**SQL_LONGVARBINARY**) をに配置することをお勧め `CByteArray` します。

との RFX 関数には `CString` `CByteArray` 追加の引数があり、これを使用すると、割り当てられたメモリの既定のサイズをオーバーライドして、データ列の取得した値を保持できます。 次の関数宣言では、nMaxLength 引数に注意してください。

```cpp
void AFXAPI RFX_Text(CFieldExchange* pFX,
    const char *szName,
    CString& value,
    int nMaxLength = 255,
    int nColumnType =
    SQL_VARCHAR);

void AFXAPI RFX_Binary(CFieldExchange* pFX,
    const char *szName,
    CByteArray& value,
    int nMaxLength = 255);
```

Long データ列をまたはに取得した場合、 `CString` `CByteArray` 返されるデータの最大量は、既定では255バイトになります。 これを超えるものは無視されます。 この場合、フレームワークは **AFX_SQL_ERROR_DATA_TRUNCATED** 例外をスローします。 幸い、nMaxLength をより大きな値にするには、 **Maxint** まで明示的に増やすことができます。

> [!NOTE]
> NMaxLength の値は、関数のローカルバッファーを設定するために MFC によって使用され `SQLBindColumn` ます。 これは、データを格納するためのローカルバッファーであり、実際には ODBC ドライバーによって返されるデータの量には影響しません。 `RFX_Text` では、 `RFX_Binary` `SQLFetch` バックエンドデータベースからデータを取得するために、を使用して呼び出しを1回だけ行います。 各 ODBC ドライバーでは、1回のフェッチで返すことができるデータの量に関して、異なる制限があります。 この制限は、nMaxLength で設定された値よりも大幅に小さくなる場合があります。この場合、例外 **AFX_SQL_ERROR_DATA_TRUNCATED** がスローされます。 このような状況では、 `RFX_LongBinary` すべての `RFX_Text` `RFX_Binary` データを取得できるように、またはの代わりに、を使用するように切り替えます。

ClassWizard は、 **SQL_LONGVARCHAR** をにバインドするか、SQL_LONGVARBINARY にバインドし `CString`  `CByteArray` ます。 長いデータ列を取得するために255バイトを超える値を割り当てる場合は、nMaxLength に明示的な値を指定できます。

長いデータ列がまたはにバインドされている場合 `CString` `CByteArray` 、フィールドの更新は、SQL_ **VARCHAR** または SQL_ **VARBINARY** にバインドされている場合と同様に動作します。 の間、データ値 `Edit` `Update` への変更を検出し、列のダーティ値と Null 値を適切に設定するためにが呼び出されたときに、データ値がキャッシュされ、後で比較されます。

## <a name="binding-a-long-data-column-to-a-clongbinary"></a>長いデータ列を CLongBinary にバインドする

長いデータ列に、より多くの **Maxint** バイトのデータが含まれている可能性がある場合は、に取得することを検討してください `CLongBinary` 。

利点:

これにより、使用可能なメモリまでの長いデータ列全体が取得されます。

短所:

データはメモリに保持されます。 この方法は、非常に大量のデータの場合にも非常に高価です。 `SetFieldDirty`フィールドが操作に含まれるようにするには、バインドされたデータメンバーに対してを呼び出す必要があり `Update` ます。

長いデータ列をに取得した場合、 `CLongBinary` データベースクラスは長いデータ列の合計サイズを確認し、 `HGLOBAL` データ値全体を保持するのに十分な大きさのメモリセグメントを割り当てます。 次に、データベースクラスは、割り当てられたにデータ値全体を取得し `HGLOBAL` ます。

データソースが long データ列の予想サイズを返すことができない場合、フレームワークは **AFX_SQL_ERROR_SQL_NO_TOTAL** 例外をスローします。 を割り当てようとして失敗した場合は、 `HGLOBAL` 標準メモリ例外がスローされます。

ClassWizard は、 **SQL_LONGVARCHAR** または **SQL_LONGVARBINARY** をにバインドし `CLongBinary` ます。 [ `CLongBinary` メンバー変数の追加] ダイアログボックスで変数の型としてを選択します。 その後、ClassWizard は `RFX_LongBinary` 呼び出しの呼び出しを追加し、バインドされた `DoFieldExchange` フィールドの合計数を増やします。

長いデータ列の値を更新するには、まず `HGLOBAL` 、の *m_hData* メンバーに対して **:: globalsize** を呼び出して、割り当てられたが新しいデータを保持するのに十分な大きさであることを確認し `CLongBinary` ます。 小さすぎる場合は、を解放 `HGLOBAL` し、適切なサイズで割り当てます。 次に、新しいサイズを反映するように *m_dwDataLength* を設定します。

それ以外の場合、 *m_dwDataLength* が置換するデータのサイズより大きい場合は、を解放して再割り当てするか、割り当てたままにしておくことができ `HGLOBAL` ます。 *M_dwDataLength* で実際に使用されているバイト数を必ず指定してください。

## <a name="how-updating-a-clongbinary-works"></a>CLongBinary の更新のしくみ

を更新する方法を理解する必要はありません `CLongBinary` が、次に説明する3番目の方法を選択した場合、データソースに長いデータ値を送信する方法の例として役立つことがあります。

> [!NOTE]
> `CLongBinary`フィールドを更新に含めるには、フィールドに対して明示的にを呼び出す必要があり `SetFieldDirty` ます。 Null の設定など、フィールドに変更を加える場合は、を呼び出す必要があり `SetFieldDirty` ます。 また `SetFieldNull` 、を呼び出して、2番目のパラメーターを **FALSE** に設定し、フィールドを値としてマークする必要があります。

フィールドを更新する場合 `CLongBinary` 、データベースクラスは odbc の **DATA_AT_EXEC** 機構を使用します (rgbValue 引数に関する odbc ドキュメントを参照してください `SQLSetPos` )。 フレームワークが insert ステートメントまたは update ステートメントを準備するときに、データを含むをポイントするのではなく、の `HGLOBAL` *アドレス* `CLongBinary` が列の *値* として設定され、長さインジケーターが **SQL_DATA_AT_EXEC** に設定されます。 その後、update ステートメントがデータソースに送信されると、 `SQLExecDirect` は **SQL_NEED_DATA** を返します。 これは、この列の param の値が実際にのアドレスであることをフレームワークに通知し `CLongBinary` ます。 フレームワークは、 `SQLGetData` 小さなバッファーを使用して1回を呼び出し、ドライバーがデータの実際の長さを返すことを想定しています。 ドライバーがバイナリラージオブジェクト (BLOB) の実際の長さを返す場合、MFC は BLOB をフェッチするために必要なだけ領域を再割り当てします。 データソースが **SQL_NO_TOTAL** を返し、BLOB のサイズを特定できないことを示している場合、MFC は小さいブロックを作成します。 既定の初期サイズは64K で、後続のブロックは2倍のサイズになります。たとえば、2番目のは128K、3番目は256K、などです。 初期サイズは構成可能です。

## <a name="not-binding-retrievingsending-data-directly-from-odbc-with-sqlgetdata"></a>バインドされていません: SQLGetData を使用して ODBC から直接データを取得/送信する

この方法では、データベースクラスを完全にバイパスし、長いデータ列を自分で処理します。

利点:

必要に応じてデータをディスクにキャッシュしたり、取得するデータ量を動的に決定したりすることができます。

短所:

フレームワークまたはサポートがないため、 `Edit` `AddNew` 基本的な機能を実行するためにコードを自分で記述する必要があり `Delete` ます (これは列レベルの操作ではないため、動作します)。

この場合、長いデータ列はレコードセットの選択リストに含まれている必要がありますが、フレームワークによってバインドされることはできません。 これを行う1つの方法として、またはを使用して独自の SQL ステートメントを指定し、 `GetDefaultSQL` 関数の lpszSQL 引数として使用して、 `CRecordset` `Open` 余分な列を RFX_ 関数呼び出しでバインドしないようにします。 ODBC では、バインドされたフィールドの右側にバインドされていないフィールドが表示されるため、バインドされていない列または列を選択リストの末尾に追加します。

> [!NOTE]
> 長いデータ列はフレームワークによってバインドされていないため、この列への変更は、の呼び出しでは処理されません `CRecordset::Update` 。 必要な SQL **INSERT** ステートメントと **UPDATE** ステートメントを作成し、送信する必要があります。

## <a name="see-also"></a>関連項目

[番号別テクニカルノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカルノート](../mfc/technical-notes-by-category.md)
