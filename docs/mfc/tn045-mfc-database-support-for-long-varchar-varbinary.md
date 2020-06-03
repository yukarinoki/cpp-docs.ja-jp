---
title: 'TN045: MFC データベースサポート (長い varchar-Varbinary)'
ms.date: 11/04/2016
helpviewer_keywords:
- TN045
- Varbinary data type
- Varchar data type
ms.assetid: cf572c35-5275-45b5-83df-5f0e36114f40
ms.openlocfilehash: 55a68ba970d0a26163f426d51818c701c13ed051
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750287"
---
# <a name="tn045-mfcdatabase-support-for-long-varcharvarbinary"></a>テクニカル ノート 45: MFC/データベースの Long Varchar/Varbinary 型のサポート

> [!NOTE]
> 次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。

この資料では、MFC データベース クラスを使用して ODBC **SQL_LONGVARCHAR**と**SQL_LONGVARBINARY**データ型を取得および送信する方法について説明します。

## <a name="overview-of-long-varcharvarbinary-support"></a>長いバーチャル/変数のサポートの概要

ODBC **SQL_LONG_VARCHAR**と**SQL_LONGBINARY**データ型 (ここでは長いデータ列と呼びます) は、膨大な量のデータを保持できます。 このデータを処理するには、次の 3 つの方法があります。

- にバインドします`CString`/`CByteArray`。

- にバインドします`CLongBinary`。

- データベース クラスとは無関係に、バインドして長いデータ値を手動で取得および送信しないでください。

3つの方法のそれぞれは利点と欠点を有する。

クエリのパラメーターでは、長いデータ列はサポートされていません。 出力列でのみサポートされます。

## <a name="binding-a-long-data-column-to-a-cstringcbytearray"></a>長いデータ列を C 文字列/C バイト配列にバインドする

長所:

この方法は理解が簡単で、使い慣れたクラスを使用します。 フレームワークは、`CFormView`の`CString`サポート`DDX_Text`を提供します。 and`CByteArray`クラスには、多くの汎用文字列またはコレクション`CString`機能があり、データ値を保持するためにローカルに割り当てられるメモリの量を制御できます。 フレームワークは、呼び出し中または`Edit``AddNew`関数呼び出し中にフィールド データの古いコピーを保持し、フレームワークは自動的にデータへの変更を検出できます。

> [!NOTE]
> 文字`CString`データを操作し`CByteArray`、バイナリ データを操作するために設計されているので、 文字データ (**SQL_LONGVARCHAR**) を に`CString`、バイナリ データ (**SQL_LONGVARBINARY**)`CByteArray`を に入れておくことをお勧めします。

RFX 関数と`CString``CByteArray`、データ列の取得された値を保持するために割り当てられたメモリの既定のサイズを上書きできる追加の引数があります。 次の関数宣言の nMaxLength 引数に注意してください。

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

長いデータ列を a`CString`または`CByteArray`に取得する場合、デフォルトでは、返されるデータの最大量は 255 バイトです。 これ以上のものは無視されます。 この場合、フレームワークは例外**をスローAFX_SQL_ERROR_DATA_TRUNCATED。** さいわい **、maxINT**まで、より大きな値に明示的に nMaxLength を増やすことができます。

> [!NOTE]
> nMaxLength の値は、関数のローカル バッファーを設定するために`SQLBindColumn`MFC によって使用されます。 これはデータを格納するためのローカル バッファーであり、ODBC ドライバーによって返されるデータの量には実際には影響しません。 `RFX_Text`バックエンド`RFX_Binary`データベースからデータを`SQLFetch`取得するために使用する呼び出しは 1 回だけです。 各 ODBC ドライバには、1 回のフェッチで返すことのできるデータ量に対して、異なる制限があります。 この制限は nMaxLength に設定された値よりはるかに小さい場合があり、その場合は例外**AFX_SQL_ERROR_DATA_TRUNCATED**がスローされます。 このような状況では、すべてのデータを`RFX_LongBinary`取得できるように`RFX_Text`、`RFX_Binary`または代わりに using に切り替えます。

クラス ウィザードは **、SQL_LONGVARCHAR**を`CString`にバインドするか、または`CByteArray` **SQL_LONGVARBINARY**を にバインドします。 長いデータ列を取り出す 255 バイトを超えるバイトを割り当てる場合は、nMaxLength に明示的な値を指定できます。

長いデータ`CString`列が`CByteArray`または にバインドされている場合、フィールドの更新は、SQL_**VARCHAR**または**VARBINARY**にバインドされている場合と同じように動作SQL_。 の`Edit`間に、データ値がキャッシュされ、後でデータ`Update`値の変更を検出し、列のダーティ値と NULL 値を適切に設定するために呼び出されたときに比較されます。

## <a name="binding-a-long-data-column-to-a-clongbinary"></a>長いデータ列を CLong バイナリにバインドする

長いデータ列に含まれる**MAXINT**バイト数が多い場合は、おそらくそれを`CLongBinary`.

長所:

これにより、使用可能なメモリまで、長いデータ列全体が取得されます。

短所:

データはメモリに保持されます。 このアプローチは、非常に大量のデータに対しても非常に高価です。 フィールドが操作`SetFieldDirty`に含まれるように、バインドされたデータ メンバーを呼び`Update`出す必要があります。

長いデータ列`CLongBinary`をに取り込む場合、データベース クラスは長いデータ列の合計サイズをチェックし`HGLOBAL`、データ値全体を保持するのに十分な大きさのメモリ セグメントを割り当てます。 その後、データベース クラスは、割り当てられた`HGLOBAL`データ値全体を取得します。

データ ソースが長いデータ列の予想サイズを返すことができない場合、フレームワークは例外**AFX_SQL_ERROR_SQL_NO_TOTAL**スローします。 割り当てが失敗`HGLOBAL`すると、標準メモリ例外がスローされます。

クラスウィザードは **、SQL_LONGVARCHAR**または**SQL_LONGVARBINARY**を`CLongBinary`あなたのためにバインドします。 [`CLongBinary`メンバー変数の追加] ダイアログで[変数の種類] を選択します。 その後、ClassWizard`RFX_LongBinary`によって`DoFieldExchange`呼び出しが追加され、バインドされたフィールドの合計数が増加します。

長いデータ列の値を更新するには、まず、割`HGLOBAL`り当てられた値が、m_hData*のメンバー*に対して **::GlobalSize**を`CLongBinary`呼び出して、新しいデータを保持するのに十分な大きさであることを確認します。 小さすぎる場合は、 を`HGLOBAL`解放し、適切なサイズを割り当てます。 次*に、* 新しいサイズを反映するようにm_dwDataLengthを設定します。

それ以外の場合 *、m_dwDataLength*が置き換えるデータのサイズよりも大きい場合は、`HGLOBAL`を解放して再割り当てするか、割り当てたままにします。 *m_dwDataLength*で実際に使用されているバイト数を必ず示してください。

## <a name="how-updating-a-clongbinary-works"></a>CLong バイナリの更新のしくみ

動作の更新`CLongBinary`方法を理解する必要はありませんが、後述するこの 3 番目の方法を選択した場合に、長いデータ値をデータ ソースに送信する方法の例として役立つ場合があります。

> [!NOTE]
> フィールドを`CLongBinary`更新に含めるには、そのフィールドを明示的に呼び出`SetFieldDirty`す必要があります。 フィールドに対して Null の設定を含む変更を行った場合`SetFieldDirty`は、 を呼び出す必要があります。 また、2`SetFieldNull`番目のパラメータを**FALSE**にして、 フィールドに値を付けるマークを付けるには、 を呼び出す必要があります。

フィールドを`CLongBinary`更新する場合、データベース クラスは ODBC の**DATA_AT_EXEC**メカニズムを使用します`SQLSetPos`('s rgbValue 引数の ODBC ドキュメントを参照してください)。 フレームワークが挿入または更新ステートメントを準備する際に`HGLOBAL`、データを含むステートメントを指すのではなく、 の*address*`CLongBinary`アドレスが列の*値*として設定され、長さ標識が**SQL_DATA_AT_EXEC**に設定されます。 後で、update ステートメントがデータ ソースに送信されると`SQLExecDirect`、 **SQL_NEED_DATA**が返されます。 この値は、この列のパラメータの値が実際には`CLongBinary`. フレームワークは、`SQLGetData`ドライバーがデータの実際の長さを返すことを期待して、小さなバッファーで一度呼び出します。 ドライバーは、バイナリ ラージ オブジェクト (BLOB) の実際の長さを返す場合、MFC は、BLOB をフェッチするために必要なだけ多くの領域を再割り当てします。 データ ソースが**blob**のサイズを決定できないというSQL_NO_TOTALを返す場合、MFC は小さいブロックを作成します。 デフォルトの初期サイズは 64K で、後続のブロックは 2 倍のサイズになります。たとえば、2 番目の値は 128K、3 番目は 256K、その他の値になります。 初期サイズは設定可能です。

## <a name="not-binding-retrievingsending-data-directly-from-odbc-with-sqlgetdata"></a>バインドしない: SQLGetData を使用して ODBC から直接データを取得/送信する

この方法では、データベースクラスを完全にバイパスし、長いデータ列を自分で処理します。

長所:

必要に応じてデータをディスクにキャッシュしたり、取得するデータの量を動的に決定したりできます。

短所:

フレームワーク`Edit`や`AddNew`サポートを受け取らないし、基本的な機能を実行するためにコードを記述する必要があります`Delete`(ただし、それは列レベルの操作ではないため、動作します)。

この場合、long データ列はレコードセットの選択リストに含まれている必要がありますが、フレームワークによってバインドすることはできません。 これを行う 1 つの方法は、関数に`GetDefaultSQL`lpszSQL 引数を介して`CRecordset`または`Open`lpszSQL 引数として独自の SQL ステートメントを指定し、余分な列をRFX_関数呼び出しでバインドしないことです。 ODBC では、バインドされていないフィールドがバインドされたフィールドの右側に表示される必要があるため、非連結列を選択リストの末尾に追加します。

> [!NOTE]
> 長いデータ列はフレームワークによってバインドされないため、変更は呼び出しでは`CRecordset::Update`処理されません。 必要な SQL **INSERT**ステートメントおよび**UPDATE**ステートメントを自分で作成して送信する必要があります。

## <a name="see-also"></a>関連項目

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)
