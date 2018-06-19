---
title: 'TN045: Long Varchar、Varbinary の MFC データベース サポート |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.data
dev_langs:
- C++
helpviewer_keywords:
- TN045
- Varbinary data type
- Varchar data type
ms.assetid: cf572c35-5275-45b5-83df-5f0e36114f40
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bd5201661afcdf6f4ae9676323f3f644817bcf7d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33386081"
---
# <a name="tn045-mfcdatabase-support-for-long-varcharvarbinary"></a>テクニカル ノート 45: MFC/データベースの Long Varchar/Varbinary 型のサポート
> [!NOTE]
>  次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。  
  
 このメモを取得し、ODBC を送信する方法を説明する**SQL_LONGVARCHAR**と**SQL_LONGVARBINARY** MFC を使用してデータ型のデータベース クラスです。  
  
## <a name="overview-of-long-varcharvarbinary-support"></a>Long Varchar/Varbinary サポートの概要  
 ODBC **SQL_LONG_VARCHAR**と**SQL_LONGBINARY** (長のデータ列とここで呼ばれる) のデータ型は、大量のデータを保持できます。 このデータを処理する 3 つの方法があります。  
  
-   バインドする`CString` /`CByteArray`です。  
  
-   バインドする`CLongBinary`です。  
  
-   ありませんすべてのバインドしを取得して、長い形式のデータ値を手動で送信、データベース クラスに依存しません。  
  
 3 つのメソッドのそれぞれの長所と短所  
  
 長い形式のデータ列がクエリにパラメーターのサポートされていません。 これらは outputColumns でのみサポートします。  
  
## <a name="binding-a-long-data-column-to-a-cstringcbytearray"></a>CString/CByteArray への長い形式のデータ列のバインド  
 利点:  
  
 この方法はわかりやすく、および使い慣れたクラスを使用します。 フレームワークを提供`CFormView`サポート`CString`で`DDX_Text`です。 一般的な文字列またはコレクションの機能の多くがある、`CString`と`CByteArray`クラス、およびするが、データ値を保持するためにローカルで割り当てられたメモリの量を制御できます。 フレームワークは、古い中にフィールドのデータのコピーを保持**編集**または`AddNew`関数呼び出しと、フレームワークは、データへの変更を自動的に検出します。  
  
> [!NOTE]
>  `CString`文字データを操作するために設計されていますが、`CByteArray`バイナリ データで作業をお勧め、文字データを配置すること (**SQL_LONGVARCHAR**) に`CString`、およびバイナリ データ (**SQL_LONGVARBINARY**) に`CByteArray`です。  
  
 RFX 関数の`CString`と`CByteArray`追加の引数がある、取得するデータ列の値を保持するために割り当てられたメモリの既定のサイズをオーバーライドすることができます。 次の関数宣言で格納引数に注意してください。  
  
```  
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
  
 長い形式のデータ列に挿入を取得する場合、`CString`または`CByteArray`最大のデータの量は、既定では、255 バイトが返されます。 これを超えるものは無視されます。 ここでは、例外がスローされます**AFX_SQL_ERROR_DATA_TRUNCATED**です。 さいわい、増やすことができますに明示的に大きい値に、格納まで**MAXINT**です。  
  
> [!NOTE]
>  MFC でのローカル バッファーを設定する格納の値が使用する、 **SQLBindColumn**関数。 これは、データの記憶域用のローカル バッファーであり、ODBC ドライバーによって返されるデータの量を実際には影響しません。 `RFX_Text` および`RFX_Binary`加えるを使用して呼び出す 1 つだけ**SQLFetch**バック エンド データベースからデータを取得します。 各 ODBC ドライバーでは、1 回のフェッチで返すことがデータの量にさまざまな制限があります。 この制限は場合、例外の場合は、格納に設定された値よりも大幅に小さくなる可能性があります**AFX_SQL_ERROR_DATA_TRUNCATED**がスローされます。 このような状況下での使用に切り替える`RFX_LongBinary`の代わりに`RFX_Text`または`RFX_Binary`すべてのデータを取得できるようにします。  
  
 ClassWizard は、バインド、 **SQL_LONGVARCHAR**を`CString`、または**SQL_LONGVARBINARY**を`CByteArray`をします。 255 バイトより大きく、長い形式のデータ列を取得する先を割り当てる場合は、格納の明示的な値を指定することができます。  
  
 長い形式のデータ列のバインド時、`CString`または`CByteArray`、フィールドを更新する sql _ にバインドされている場合と同様のしくみ**VARCHAR**または sql _**VARBINARY**です。 中に**編集**、休暇から以降場合と比較して、データ値がキャッシュされる**更新**値のデータへの変更、および、Dirty を設定し、列の値を適切に Null を検出するために呼び出されます。  
  
## <a name="binding-a-long-data-column-to-a-clongbinary"></a>CLongBinary への長い形式のデータ列のバインド  
 複数の長い形式のデータ列が含まれます場合**MAXINT**データのバイト数は、おそらくを検討してくださいに取得する、`CLongBinary`です。  
  
 利点:  
  
 これには、最大で使用可能なメモリ、全体の長い形式のデータ列を取得します。  
  
 欠点:  
  
 データは、メモリに保持されます。 この方法は非常に大量のデータの負担もあります。 呼び出す必要があります`SetFieldDirty`にバインドされたデータのフィールドを確認するにはメンバーが含まれている、**更新**操作します。  
  
 長い形式のデータ列を取得する場合、 `CLongBinary`、データベース クラスは、長い形式のデータ列の合計サイズを確認してからを割り当てて、`HGLOBAL`メモリ セグメントのデータ値全体を保持するのに十分です。 データベース クラスは、割り当てられたに全体のデータ値を取得`HGLOBAL`です。  
  
 フレームワークが例外をスローする場合は、データ ソースには、長い形式のデータ列の予想サイズを返すことはできません、**返せない場合**です。 場合を割り当てようとした、`HGLOBAL`が失敗した、標準的なメモリ例外がスローされます。  
  
 ClassWizard は、バインド、 **SQL_LONGVARCHAR**または**SQL_LONGVARBINARY**を`CLongBinary`します。 選択`CLongBinary`メンバー変数の追加のダイアログ ボックスで変数の型として。 ClassWizard は追加して、`RFX_LongBinary`への呼び出し、`DoFieldExchange`を呼び出すし、バインドされたフィールドの合計数をインクリメントします。  
  
 長いデータ列値を更新するには、最初に確認、割り当てられた`HGLOBAL`を呼び出すことによって、新しいデータを保持するのに十分な大きさが **:: GlobalSize**上、`m_hData`のメンバー、`CLongBinary`です。 小さすぎる場合は、リリース、`HGLOBAL`し、1 つに、適切なサイズを割り当てます。 `m_dwDataLength`新しいサイズを反映するようにします。  
  
 それ以外の場合`m_dwDataLength`サイズよりも大きい、置換するデータのいずれかを解放して再割り当て、 `HGLOBAL`、か、割り当てられたままにします。 実際に使用されているバイト数を示す確認`m_dwDataLength`です。  
  
## <a name="how-updating-a-clongbinary-works"></a>CLongBinary 動作を更新する方法  
 理解する必要はありません更新方法、`CLongBinary`動作しますが、これは、データ ソースを長い形式のデータ値を送信する方法の例としてに利用できる以下に示すこの 3 番目の方法を選択するかどうか。  
  
> [!NOTE]
>  順序で、 `CLongBinary` 、更新プログラムに含まれるフィールドに明示的に呼び出す必要があります`SetFieldDirty`フィールドです。 Null に設定を含むフィールドを変更する必要がありますを呼び出した場合`SetFieldDirty`です。 呼び出す必要があります`SetFieldNull`、2 番目のパラメーターの中で**FALSE**値を持つものとしてフィールドを設定する。  
  
 更新するときに、`CLongBinary`フィールドでは、データベース クラスの使用 ODBC の**DATA_AT_EXEC**メカニズム (ODBC のドキュメントを参照して**SQLSetPos**の rgbValue 引数)。 フレームワークが指すのではなく、insert または update ステートメントを準備するときに、 `HGLOBAL` 、データを含む、*アドレス*の`CLongBinary`として設定されている、*値*列の代わりに、および長さのインジケーターに設定**SQL_DATA_AT_EXEC**です。 その後、update ステートメントが、データ ソースに送信される**SQLExecDirect**戻ります**SQL_NEED_DATA**です。 これは、アラートは、framework この列のパラメーターの値が実際のアドレスである、`CLongBinary`です。 フレームワークによって**SQLGetData** 1 回小さなバッファーを伴うデータの実際の長さを返すことを指定してください。 場合は、ドライバーでは、バイナリ ラージ オブジェクト (BLOB) の実際の長さを返します、MFC には、BLOB をフェッチする必要に応じて多くの領域が再割り当ています。 場合は、データ ソースを返します**SQL_NO_TOTAL**BLOB のサイズを特定できないことを示す、MFC はより小さなブロックが作成されます。 既定の初期サイズは 64 K、および後続のブロック サイズ; の 2 倍になりますたとえば、3 つ目は、256 K の 2 番目を 128 K となります。 初期サイズは構成可能です。  
  
## <a name="not-binding-retrievingsending-data-directly-from-odbc-with-sqlgetdata"></a>バインドがありません: 取得する/データの送信 SQLGetData と ODBC から直接  
 このメソッドを使用して完全に省略データベース クラスされ、長い形式のデータ列を処理します。  
  
 利点:  
  
 必要に応じて、ディスクまたは取得するデータの量を動的に決定するデータをキャッシュすることができます。  
  
 欠点:  
  
 フレームワークの取得しない**編集**または`AddNew`サポート、およびするが記述する必要があります基本的な機能を実行する独自のコード (**削除**の機能は、列レベルの操作ではないため)。  
  
 この場合、長い形式のデータ列は、レコード セットの選択リストである必要がありますが、フレームワークによってにバインドされていません。 これを行うには 1 つの方法を使用して、独自の SQL ステートメントを指定する`GetDefaultSQL`や lpszSQL 引数として`CRecordset`の**開く**機能、rfx _ 関数呼び出しに余分な列をバインドできません。 そのため、選択リストの末尾に非バインド列または列を追加、ODBC の連結されていないフィールドがバインドされたフィールドの右側に表示されることが必要です。  
  
> [!NOTE]
>  フレームワークによって、長い形式のデータ列がバインドされていないために変更するは処理されない`CRecordset::Update`呼び出しです。 作成して、必要な SQL を送信する必要があります**挿入**と**更新**ステートメント自分でします。  
  
## <a name="see-also"></a>関連項目  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)

