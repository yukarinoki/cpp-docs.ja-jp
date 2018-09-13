---
title: 'MFC ActiveX コントロール: トピックを Advanced |Microsoft Docs'
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fbebffa1bbec55e08cccafd387c44991ebe467ca
ms.sourcegitcommit: b4432d30f255f0cb58dce69cbc8cbcb9d44bc68b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2018
ms.locfileid: "45535253"
---
# <a name="mfc-activex-controls-advanced-topics"></a>MFC ActiveX コントロール : 高度なトピック
この記事では、ActiveX コントロールの開発に関連する高度なトピックについて説明します。 次の設定があります。  
  
-   [ActiveX コントロールにおけるデータベース クラスの使用](#_core_using_database_classes_in_activex_controls)  
  
-   [パラメーター化されたプロパティを実装します。](#_core_implementing_a_parameterized_property)  
  
-   [ActiveX コントロールでのエラーを処理](#_core_handling_errors_in_your_activex_control)  
  
-   [コントロール内の特殊なキーの処理](#_core_handling_special_keys_in_your_control)  
  
-   [実行時に表示されないダイアログ コントロールへのアクセス](#_core_accessing_dialog_controls_that_are_invisible_at_run_time)  

>[!IMPORTANT]
> ActiveX は、新規の開発が使用できないレガシ テクノロジです。 ActiveX の上書きの最新のテクノロジの詳細については、次を参照してください。 [ActiveX コントロール](activex-controls.md)します。
  
##  <a name="_core_using_database_classes_in_activex_controls"></a> ActiveX コントロールにおけるデータベース クラスの使用  
 ActiveX コントロールのクラスは、クラス ライブラリの一部であるために、同じ手順と MFC データベース クラスを使用する ActiveX コントロールの開発に標準の MFC アプリケーションでデータベース クラスの使用に関する規則を適用できます。  
  
 MFC データベース クラスの一般的な概要については、次を参照してください。 [MFC データベース クラス (DAO と ODBC)](../data/mfc-database-classes-odbc-and-dao.md)します。 この記事では MFC ODBC クラスと MFC DAO クラスしの詳細については、いずれかを紹介します。  
  
> [!NOTE]
>  Visual C 環境とウィザードは、(DAO クラスが含まれていますし、それらを使用することもできます) が DAO をサポートしています。 使用することをお勧めします。 [OLE DB テンプレート](../data/oledb/ole-db-programming.md)または[ODBC と MFC](../data/odbc/odbc-and-mfc.md)の新しいプロジェクト。 DAO は、既存のアプリケーションを維持するためにのみ使用する必要があります。  
  
##  <a name="_core_implementing_a_parameterized_property"></a> パラメーター化されたプロパティを実装します。  
 パラメーター化されたプロパティ (プロパティの配列とも呼ばれます) は、コントロールの 1 つのプロパティと値の同種のコレクションを公開するためのメソッドです。 たとえば、パラメーター化されたプロパティを使用すると、配列またはディクショナリをプロパティとして公開します。 Visual basic で配列表記を使用してこのようなプロパティにアクセスします。  
  
 [!code-vb[NVC_MFC_AxVb#1](../mfc/codesnippet/visualbasic/mfc-activex-controls-advanced-topics_1.vb)]  
  
 パラメーター化されたプロパティを実装するのにには、プロパティの追加ウィザードを使用します。 プロパティの追加ウィザードでは、上記の表記を使用してプロパティにアクセスするユーザーが制御できる取得/設定関数または標準の方法でのペアを追加することで、プロパティを実装します。  
  
 同様に、メソッドとプロパティ、パラメーター化されたプロパティも使用できるパラメーターの数に制限があります。 パラメーター化されたプロパティは、の場合は、制限は、15 個のパラメーター (1 つのパラメーター プロパティの値を格納するために予約されています) とは。  
  
 次の手順では、整数の 2 次元の配列としてアクセスできる配列と呼ばれる、パラメーター化されたプロパティを追加します。  
  
#### <a name="to-add-a-parameterized-property-using-the-add-property-wizard"></a>プロパティの追加ウィザードを使用してパラメーター化されたプロパティを追加するには  
  
1.  コントロールのプロジェクトを読み込みます。  
  
2.  [クラス ビュー] で、コントロールのライブラリ ノードを展開します。  
  
3.  コントロールのインターフェイス ノード (ライブラリ ノードの 2 番目のノード) を右クリックし、ショートカット メニューを開きます。  
  
4.  ショートカット メニューでは、次のようにクリックします。**追加** をクリックし、**プロパティの追加**します。  
  
5.  **プロパティ名**ボックスに「`Array`します。  
  
6.  **プロパティ型**ボックスで、**短い**します。  
  
7.  **実装**型、 をクリックして**Get/set メソッド**します。  
  
8.  **Get 関数**と**設定関数**ボックス、Get と Set 関数の一意の名前を入力するか、既定の名前をそのまま使用します。  
  
9. という名前のパラメーターを追加*行*(型*短い*) を使用して、**パラメーター名**と**パラメーターの型**コントロール。  
  
10. 呼ばれる 2 番目のパラメーターを追加*列*(型*短い*)。  
  
11. **[完了]** をクリックします。  
  
### <a name="changes-made-by-the-add-property-wizard"></a>によって行われた変更、プロパティの追加ウィザード  
 プロパティの追加ウィザードが、コントロール クラスのヘッダーに変更をによってカスタム プロパティを追加すると (します。H) と実装 (します。CPP) ファイル。  
  
 次の行は、コントロール クラスに追加されます。H ファイル:  
  
 [!code-cpp[NVC_MFC_AxUI#35](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_2.h)]  
  
 このコードと呼ばれる 2 つの関数を宣言して`GetArray`と`SetArray`プロパティにアクセスするときに、特定の行と列を要求するユーザーを許可します。  
  
 コントロールのコントロール クラスの実装にあるディスパッチ マップにさらに、プロパティの追加ウィザードが次の行を追加します (します。CPP) ファイル:  
  
 [!code-cpp[NVC_MFC_AxUI#36](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_3.cpp)]  
  
 実装では最後に、`GetArray`と`SetArray`関数の末尾に追加します。CPP ファイルです。 ほとんどの場合は、プロパティの値を返す Get 関数を変更します。 Set 関数には、通常、プロパティの変更の前後どちらでも、実行されるコードが含まれます。  
  
 このプロパティを使用するには、コントロール クラスの型の 2 次元配列のメンバー変数を宣言できます**短い**、パラメーター化されたプロパティの値を格納します。 パラメーターで示されている適切な行と列に格納された値を返す Get 関数を変更し、行と列パラメーターによって参照される値を更新するセット関数を変更可能性があります。  
  
##  <a name="_core_handling_errors_in_your_activex_control"></a> ActiveX コントロールでのエラーを処理  
 コントロール内のエラーが発生した場合は、コントロール コンテナーに、エラーを報告する必要があります。 エラーが発生した状況に応じて、エラー報告の 2 つの方法はあります。 プロパティの取得エラーが発生した場合、または関数を OLE オートメーション メソッドの実装内でコントロールを呼び出す必要がありますまたは[COleControl::ThrowError](../mfc/reference/colecontrol-class.md#throwerror)エラーが発生したコントロールのユーザーにどの信号。 その他の任意の時点で、エラーが発生した場合、コントロールを呼び出す必要があります[COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror)、株価のエラー イベントが発生します。  
  
 コントロールで発生したエラーの種類を示すエラー コードを渡す必要があります`ThrowError`または`FireError`します。 エラー コードは、32 ビットの値を持つ OLE ステータス コードです。 可能であれば、エラー コードをとして使用で定義されたコードの標準セットから選択します。H ヘッダー ファイルです。 次の表では、これらのコードを示します。  
  
### <a name="activex-control-error-codes"></a>ActiveX コントロール エラー コード  
  
|Error|説明|  
|-----------|-----------------|  
|CTL_E_ILLEGALFUNCTIONCALL|無効な関数呼び出し|  
|CTL_E_OVERFLOW|オーバーフロー|  
|CTL_E_OUTOFMEMORY|メモリ不足|  
|CTL_E_DIVISIONBYZERO|0 による除算|  
|CTL_E_OUTOFSTRINGSPACE|文字列スペース|  
|CTL_E_OUTOFSTACKSPACE|スタック領域不足|  
|CTL_E_BADFILENAMEORNUMBER|ファイル名または番号が正しくありません。|  
|CTL_E_FILENOTFOUND|ファイルが見つかりませんでした。|  
|CTL_E_BADFILEMODE|ファイル モードが正しくありません。|  
|CTL_E_FILEALREADYOPEN|ファイルは既に開かれています。|  
|CTL_E_DEVICEIOERROR|デバイス I/O エラーです。|  
|CTL_E_FILEALREADYEXISTS|ファイルは既に存在します|  
|CTL_E_BADRECORDLENGTH|レコード長が正しくありません。|  
|CTL_E_DISKFULL|ディスクがいっぱいです。|  
|CTL_E_BADRECORDNUMBER|レコード番号が正しくありません|  
|CTL_E_BADFILENAME|不適切なファイル名|  
|CTL_E_TOOMANYFILES|ファイルが多すぎます。|  
|CTL_E_DEVICEUNAVAILABLE|デバイスが準備されていません|  
|CTL_E_PERMISSIONDENIED|アクセス許可は拒否されました|  
|CTL_E_DISKNOTREADY|ディスクが準備されていません|  
|CTL_E_PATHFILEACCESSERROR|パス/ファイル アクセス エラー|  
|CTL_E_PATHNOTFOUND|パスが見つかりません。|  
|CTL_E_INVALIDPATTERNSTRING|正しくないパターン文字列|  
|CTL_E_INVALIDUSEOFNULL|無効な NULL の使用|  
|CTL_E_INVALIDFILEFORMAT|無効なファイルの形式|  
|CTL_E_INVALIDPROPERTYVALUE|無効なプロパティ値|  
|CTL_E_INVALIDPROPERTYARRAYINDEX|無効なプロパティの配列インデックス|  
|CTL_E_SETNOTSUPPORTEDATRUNTIME|Set は実行時にはサポートされません|  
|CTL_E_SETNOTSUPPORTED|Set はサポートされません。読み取り専用のプロパティです。|  
|CTL_E_NEEDPROPERTYARRAYINDEX|プロパティ配列のインデックスが必要です。|  
|CTL_E_SETNOTPERMITTED|Set は使用できません|  
|CTL_E_GETNOTSUPPORTEDATRUNTIME|Get は実行時にはサポートされません|  
|CTL_E_GETNOTSUPPORTED|Get はサポートされません。書き込み専用のプロパティです|  
|CTL_E_PROPERTYNOTFOUND|プロパティが見つかりません。|  
|CTL_E_INVALIDCLIPBOARDFORMAT|無効なクリップボード形式|  
|CTL_E_INVALIDPICTURE|無効な画像|  
|CTL_E_PRINTERERROR|プリンター エラーです|  
|CTL_E_CANTSAVEFILETOTEMP|ファイルを TEMP に保存することはできません。|  
|CTL_E_SEARCHTEXTNOTFOUND|検索文字列が見つかりませんでした|  
|CTL_E_REPLACEMENTSTOOLONG|置換後の文字列が長すぎます|  
  
 必要に応じて、標準のコードのいずれかによってカバーされていない状態のカスタム エラー コードを定義するのに CUSTOM_CTL_SCODE マクロを使用します。 このマクロのパラメーターは、1000 までの整数をすることは 32767 です。 例えば:  
  
 [!code-cpp[NVC_MFC_AxUI#37](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_4.cpp)]  
  
 既存の VBX コントロールを置換する ActiveX コントロールを作成する場合は、VBX コントロールはエラー コードと互換性があることを確認します。 を使用して同じ数値の値では、ActiveX コントロール エラー コードを定義します。  
  
##  <a name="_core_handling_special_keys_in_your_control"></a> コントロール内の特殊なキーの処理  
 場合によっては; 特別な方法で特定のキーストロークの組み合わせを処理するために必要な可能性があります。などを挿入複数行テキストで ENTER キーが押されたときに、新しい行のボックス コントロールまたは編集の間を移動コントロールと、方向キーが押されました。  
  
 ActiveX コントロールの基底クラスがある場合`COleControl`、オーバーライドすることができます[cwnd::pretranslatemessage](../mfc/reference/cwnd-class.md#pretranslatemessage)コンテナーがそれらを処理する前にメッセージを処理します。 この手法を使用して場合、常に返します**TRUE**のオーバーライドで、メッセージを処理する場合`PreTranslateMessage`します。  
  
 次のコード例では、方向キーに関連するすべてのメッセージの処理方法を示します。  
  
 [!code-cpp[NVC_MFC_AxUI#38](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_5.cpp)]  
  
 ActiveX コントロールのキーボード インターフェイスの処理に関する詳細については、ActiveX SDK のドキュメントを参照してください。  
  
##  <a name="_core_accessing_dialog_controls_that_are_invisible_at_run_time"></a> 実行時に表示されないダイアログ コントロールへのアクセス  
 ユーザー インターフェイスがない実行時に表示されないダイアログ コントロールを作成することができます。 ActiveX コントロールの実行時にダイアログ ボックスを使用して、非表示を追加する場合[:getdlgitem](../mfc/reference/cwnd-class.md#getdlgitem)コントロールにアクセスするコントロールは正しく動作しません。 代わりに、コントロールを表すオブジェクトを取得するのに、次の手法のいずれかを使用する必要があります。  
  
-   追加のメンバー変数ウィザードを使用して選択**コントロール変数**し、コントロールの id。 メンバー変数の名前を入力し、として、コントロールのラッパー クラスを選択、**コントロール型**します。  
  
     - または -  
  
-   ダイアログの項目として、ローカル変数とサブクラスを宣言します。 次のようなコードを挿入 (`CMyCtrl`ラッパー クラスには、IDC_MYCTRL1 はコントロールの ID)。  
  
     [!code-cpp[NVC_MFC_AxCont#19](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_6.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)

