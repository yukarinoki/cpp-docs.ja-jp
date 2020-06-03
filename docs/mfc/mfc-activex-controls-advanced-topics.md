---
title: 'MFC ActiveX コントロール : 高度なトピック'
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- MFC ActiveX controls [MFC], accessing invisible dialog controls
- MFC ActiveX controls [MFC], advanced topics
- FireError method [MFC]
- MFC ActiveX controls [MFC], database classes
- MFC ActiveX controls [MFC], special keys
- PreTranslateMessage method [MFC]
- MFC ActiveX controls [MFC], parameterized property
- ThrowError method [MFC]
ms.assetid: e9e34abb-8e2d-461e-bb9c-a1aec5dcecbd
ms.openlocfilehash: c5e3be3915a0707f8df17d3c9ebe2eb0e4f623b2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364640"
---
# <a name="mfc-activex-controls-advanced-topics"></a>MFC ActiveX コントロール : 高度なトピック

この記事では、ActiveX コントロールの開発に関連する高度なトピックについて説明します。 これには以下が含まれます。

- [ActiveX コントロールでのデータベース クラスの使用](#_core_using_database_classes_in_activex_controls)

- [パラメーター化されたプロパティの実装](#_core_implementing_a_parameterized_property)

- [ActiveX コントロールのエラー処理](#_core_handling_errors_in_your_activex_control)

- [コントロール内の特殊キーの処理](#_core_handling_special_keys_in_your_control)

- [実行時に非表示になっているダイアログ コントロールへのアクセス](#_core_accessing_dialog_controls_that_are_invisible_at_run_time)

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX に取って代わる最新テクノロジの詳細については、「 [ActiveX コントロール](activex-controls.md)」を参照してください。

## <a name="using-database-classes-in-activex-controls"></a><a name="_core_using_database_classes_in_activex_controls"></a>ActiveX コントロールでのデータベース クラスの使用

ActiveX コントロール クラスはクラス ライブラリの一部であるため、標準 MFC アプリケーションでデータベース クラスを使用する場合と同じプロシージャと規則を適用して、MFC データベース クラスを使用する ActiveX コントロールを開発できます。

MFC データベース クラスの概要については[、「MFC データベース クラス (DAO および ODBC)」](../data/mfc-database-classes-odbc-and-dao.md)を参照してください。 この記事では、MFC ODBC クラスと MFC DAO クラスの両方について説明し、その詳細については、その説明を参照してください。

> [!NOTE]
> DAO は Office 2013 を通じてサポートされています。 DAO 3.6 は最終バージョンであり、廃止と見なされます。 Visual C++ 環境およびウィザードは DAO をサポートしていません (ただし、DAO クラスは含まれていますが、使用することはできます)。 新しいプロジェクトには[、OLE DB テンプレート](../data/oledb/ole-db-programming.md)または[ODBC および MFC](../data/odbc/odbc-and-mfc.md)を使用することをお勧めします。 DAO は、既存のアプリケーションの保守にのみ使用してください。

## <a name="implementing-a-parameterized-property"></a><a name="_core_implementing_a_parameterized_property"></a>パラメーター化されたプロパティの実装

パラメーター化されたプロパティ (プロパティ配列とも呼ばれます) は、同種の値のコレクションをコントロールの 1 つのプロパティとして公開するためのメソッドです。 たとえば、パラメーター化されたプロパティを使用して、配列またはディクショナリをプロパティとして公開できます。 Visual Basic では、このようなプロパティには、配列表記を使用してアクセスします。

[!code-vb[NVC_MFC_AxVb#1](../mfc/codesnippet/visualbasic/mfc-activex-controls-advanced-topics_1.vb)]

プロパティの追加ウィザードを使用して、パラメーター化されたプロパティを実装します。 プロパティの追加ウィザードは、上記の表記法または標準の方法でコントロール ユーザーがプロパティにアクセスできるようにする Get/Set 関数のペアを追加して、プロパティを実装します。

メソッドやプロパティと同様に、パラメーター化されたプロパティにも、許可されるパラメーターの数に制限があります。 パラメーター化されたプロパティの場合、制限は 15 個のパラメーターです (プロパティ値を格納するために予約されているパラメーターが 1 つ含まれています)。

次のプロシージャは、整数の 2 次元配列としてアクセスできる Array というパラメーター化されたプロパティを追加します。

#### <a name="to-add-a-parameterized-property-using-the-add-property-wizard"></a>プロパティの追加ウィザードを使用してパラメータ化されたプロパティを追加するには

1. コントロールのプロジェクトを読み込みます。

1. [クラス ビュー] で、コントロールのライブラリ ノードを展開します。

1. コントロールのインターフェイス ノード (ライブラリ ノードの 2 番目のノード) を右クリックし、ショートカット メニューを開きます。

1. ショートカット メニューの [**追加**] をクリックし、[**プロパティの追加**] をクリックします。

1. [**プロパティ名]** ボックスに`Array`「 」と入力します。

1. [**プロパティの種類]** ボックスで、[**短い**] を選択します。

1. **[実装**の種類] で、[**メソッドの取得/設定**] をクリックします。

1. [**関数の取得**] ボックスと **[関数の設定**] ボックスに、Get 関数と Set 関数に一意の名前を入力するか、既定の名前をそのまま使用します。

1. [パラメーター名]**コントロールと**[*パラメーターの型*] コントロールを使用して *、"row* ( short 型 " ) という**パラメータ**を追加します。

1. *column*という 2 番目のパラメータを*追加します*(short と入力します)。

1. **[完了]** をクリックします。

### <a name="changes-made-by-the-add-property-wizard"></a>プロパティの追加ウィザードによる変更

カスタム プロパティを追加すると、プロパティの追加ウィザードによってコントロール クラス ヘッダー (.H) および実装 (.CPP) ファイル。

次の行がコントロール クラス に追加されます。H ファイル:

[!code-cpp[NVC_MFC_AxUI#35](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_2.h)]

このコードは、呼び出`GetArray`される`SetArray`2 つの関数を宣言し、プロパティにアクセスするときにユーザーが特定の行と列を要求できるようにします。

さらに、プロパティの追加ウィザードは、コントロール クラスの実装 ( .CPP) ファイル:

[!code-cpp[NVC_MFC_AxUI#36](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_3.cpp)]

最後に、`GetArray`および`SetArray`関数の実装が の末尾に追加されます。CPP ファイル。 ほとんどの場合、Get 関数を変更してプロパティの値を返します。 Set 関数には、通常、プロパティの変更前または変更後に実行する必要のあるコードが含まれます。

このプロパティを有効にするには、コントロール クラスで short**型の**2 次元配列メンバー変数を宣言し、パラメーター化されたプロパティの値を格納します。 次に、パラメーターで示されているように、適切な行と列に格納されている値を返すように Get 関数を変更し、行と列のパラメーターによって参照される値を更新するように Set 関数を変更します。

## <a name="handling-errors-in-your-activex-control"></a><a name="_core_handling_errors_in_your_activex_control"></a>ActiveX コントロールのエラー処理

コントロールでエラー状態が発生した場合は、コントロール コンテナーにエラーを報告する必要があります。 エラーの報告方法は、エラーが発生した状況に応じて 2 つあります。 プロパティの Get 関数または Set 関数、または OLE オートメーション メソッドの実装内でエラーが発生した場合、コントロールは[COleControl::ThrowError](../mfc/reference/colecontrol-class.md#throwerror)を呼び出す必要があります。 エラーが発生した場合は、その他のタイミングで、コントロールは[COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror)を呼び出して、ストック エラー イベントを発生させます。

発生したエラーの種類を示すには、コントロールがエラー コードを または`ThrowError``FireError`に渡す必要があります。 エラー コードは、32 ビット値を持つ OLE 状態コードです。 可能な場合は、OLECTL で定義されている標準コード セットからエラー コードを選択します。H ヘッダー ファイル。 次の表は、これらのコードをまとめたものです。

### <a name="activex-control-error-codes"></a>ActiveX コントロールのエラー コード

|エラー|説明|
|-----------|-----------------|
|CTL_E_ILLEGALFUNCTIONCALL|無効な関数呼び出し|
|CTL_E_OVERFLOW|オーバーフロー|
|CTL_E_OUTOFMEMORY|メモリ不足|
|CTL_E_DIVISIONBYZERO|ゼロ除算|
|CTL_E_OUTOFSTRINGSPACE|文字列スペースが不足しています。|
|CTL_E_OUTOFSTACKSPACE|スタック領域が不足しています。|
|CTL_E_BADFILENAMEORNUMBER|ファイル名または番号が正しくありません。|
|CTL_E_FILENOTFOUND|ファイルが見つからない|
|CTL_E_BADFILEMODE|ファイル モードが正しくありません。|
|CTL_E_FILEALREADYOPEN|ファイルは既に開かれています。|
|CTL_E_DEVICEIOERROR|デバイス I/O エラーです。|
|CTL_E_FILEALREADYEXISTS|ファイルは既に存在します|
|CTL_E_BADRECORDLENGTH|レコード長が正しくありません。|
|CTL_E_DISKFULL|ディスクがいっぱいです|
|CTL_E_BADRECORDNUMBER|レコード番号が正しくありません|
|CTL_E_BADFILENAME|ファイル名が正しくありません|
|CTL_E_TOOMANYFILES|ファイルが多すぎます。|
|CTL_E_DEVICEUNAVAILABLE|デバイスが準備されていません|
|CTL_E_PERMISSIONDENIED|アクセス許可は拒否されました|
|CTL_E_DISKNOTREADY|ディスクが準備されていません|
|CTL_E_PATHFILEACCESSERROR|パス/ファイル アクセス エラー|
|CTL_E_PATHNOTFOUND|パスが見つかりません。|
|CTL_E_INVALIDPATTERNSTRING|正しくないパターン文字列|
|CTL_E_INVALIDUSEOFNULL|無効な NULL の使用|
|CTL_E_INVALIDFILEFORMAT|無効なファイル形式|
|CTL_E_INVALIDPROPERTYVALUE|無効なプロパティ値|
|CTL_E_INVALIDPROPERTYARRAYINDEX|プロパティ配列インデックスが無効です|
|CTL_E_SETNOTSUPPORTEDATRUNTIME|Set は実行時にはサポートされません|
|CTL_E_SETNOTSUPPORTED|Set はサポートされません。読み取り専用のプロパティです。|
|CTL_E_NEEDPROPERTYARRAYINDEX|プロパティ配列のインデックスが必要です。|
|CTL_E_SETNOTPERMITTED|Set は使用できません|
|CTL_E_GETNOTSUPPORTEDATRUNTIME|Get は実行時にはサポートされません|
|CTL_E_GETNOTSUPPORTED|Get はサポートされません。書き込み専用のプロパティです|
|CTL_E_PROPERTYNOTFOUND|プロパティが見つかりません。|
|CTL_E_INVALIDCLIPBOARDFORMAT|クリップボード形式が無効です|
|CTL_E_INVALIDPICTURE|無効な画像|
|CTL_E_PRINTERERROR|プリンター エラーです|
|CTL_E_CANTSAVEFILETOTEMP|TEMP にファイルを保存できません|
|CTL_E_SEARCHTEXTNOTFOUND|検索文字列が見つかりませんでした|
|CTL_E_REPLACEMENTSTOOLONG|置換後の文字列が長すぎます|

必要に応じて、CUSTOM_CTL_SCODE マクロを使用して、標準コードの 1 つでカバーされない条件のカスタム エラー コードを定義します。 このマクロのパラメーターは、1000 から 32767 までの整数でなければなりません。 次に例を示します。

[!code-cpp[NVC_MFC_AxUI#37](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_4.cpp)]

既存の VBX コントロールを置き換える ActiveX コントロールを作成する場合は、エラー コードに互換性を持たれるように、VBX コントロールが使用するのと同じ数値を使用して ActiveX コントロールのエラー コードを定義します。

## <a name="handling-special-keys-in-the-control"></a><a name="_core_handling_special_keys_in_your_control"></a>コントロール内の特殊キーの処理

場合によっては、特定のキーストロークの組み合わせを特別な方法で処理したい場合があります。たとえば、複数行テキスト ボックス コントロールで Enter キーを押したときに新しい行を挿入したり、方向キー ID が押されたときにエディット コントロールのグループ間を移動したりできます。

ActiveX コントロールの基本クラスが の`COleControl`場合は[、CWnd::PreTranslateMessage を](../mfc/reference/cwnd-class.md#pretranslatemessage)オーバーライドして、メッセージを処理してから、メッセージを処理できます。 この方法を使用する場合、**TRUE**メッセージを オーバーライドで処理する場合は常`PreTranslateMessage`に TRUE を返します。

次のコード例は、方向キーに関連するメッセージを処理する方法を示しています。

[!code-cpp[NVC_MFC_AxUI#38](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_5.cpp)]

ActiveX コントロールのキーボード インターフェイスの処理の詳細については、ActiveX SDK のドキュメントを参照してください。

## <a name="accessing-dialog-controls-that-are-invisible-at-run-time"></a><a name="_core_accessing_dialog_controls_that_are_invisible_at_run_time"></a>実行時に非表示になっているダイアログ コントロールへのアクセス

ユーザー インターフェイスを持たないダイアログ コントロールを作成し、実行時に非表示にできます。 実行時に ActiveX コントロールをダイアログ ボックスに追加し[、CWnd::GetDlgItem](../mfc/reference/cwnd-class.md#getdlgitem)を使用してコントロールにアクセスすると、コントロールは正しく動作しません。 代わりに、次のいずれかの方法を使用して、コントロールを表すオブジェクトを取得する必要があります。

- メンバー変数の追加ウィザードを使用して、**コントロール変数**を選択し、コントロールの ID を選択します。 メンバー変数名を入力し、コントロールのラッパー クラスを **[ コントロールの種類 ]** として選択します。

     \- または -

- ダイアログ項目としてローカル変数とサブクラスを宣言します。 次のようなコードを挿入します (`CMyCtrl`ラッパー クラス、IDC_MYCTRL1は、コントロールの ID です)。

   [!code-cpp[NVC_MFC_AxCont#19](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_6.cpp)]

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)
