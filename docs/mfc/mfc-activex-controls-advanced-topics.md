---
title: 'MFC ActiveX コントロール: 詳細事項 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: eb451abc3aabe52d9aeffbc92f80df38f02e0b99
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33354019"
---
# <a name="mfc-activex-controls-advanced-topics"></a>MFC ActiveX コントロール : 高度なトピック
この記事では、ActiveX コントロールの開発に関連する高度なトピックについて説明します。 次の設定があります。  
  
-   [ActiveX コントロールにおけるデータベース クラスの使用](#_core_using_database_classes_in_activex_controls)  
  
-   [パラメーター化されたプロパティを実装します。](#_core_implementing_a_parameterized_property)  
  
-   [ActiveX コントロールでのエラーを処理](#_core_handling_errors_in_your_activex_control)  
  
-   [コントロール内の特殊なキーの処理](#_core_handling_special_keys_in_your_control)  
  
-   [実行時に表示されないダイアログ コントロールへのアクセス](#_core_accessing_dialog_controls_that_are_invisible_at_run_time)  
  
##  <a name="_core_using_database_classes_in_activex_controls"></a> ActiveX コントロールにおけるデータベース クラスの使用  
 ActiveX コントロールのクラスは、クラス ライブラリの一部であるために、同じ手順と MFC データベース クラスを使用して ActiveX コントロールを開発する標準の MFC アプリケーションでデータベース クラスを使用するための規則を適用できます。  
  
 MFC データベース クラスの一般的な概要については、次を参照してください。 [MFC データベース クラス (DAO と ODBC)](../data/mfc-database-classes-odbc-and-dao.md)です。 アーティクルが MFC ODBC クラスを導入し、MFC DAO クラスしの詳細については、いずれかを紹介します。  
  
> [!NOTE]
>  Visual C 環境とウィザードは、(ただし、DAO クラスが含まれると、引き続き使用することができます) DAO をサポートしています。 使用することをお勧めします。 [OLE DB テンプレート](../data/oledb/ole-db-programming.md)または[ODBC と MFC](../data/odbc/odbc-and-mfc.md)新しいプロジェクトのです。 DAO は、既存のアプリケーションを保守でのみ使用する必要があります。  
  
##  <a name="_core_implementing_a_parameterized_property"></a> パラメーター化されたプロパティを実装します。  
 (プロパティ配列とも呼ばれます)、パラメーター化されたプロパティは、コントロールの 1 つのプロパティと値の同種のコレクションを公開するためのメソッドです。 たとえば、パラメーター化されたプロパティを使用して、配列またはディクショナリをプロパティとして公開することができます。 Visual basic でこのようなプロパティは、配列表記を使用してアクセスされます。  
  
 [!code-vb[NVC_MFC_AxVb#1](../mfc/codesnippet/visualbasic/mfc-activex-controls-advanced-topics_1.vb)]  
  
 パラメーター化されたプロパティを実装するのにには、プロパティの追加ウィザードを使用します。 プロパティの追加ウィザードでは、または、標準的なやり方で上記の表記を使用してプロパティにアクセスするユーザーが制御できる取得/設定関数のペアを追加することで、プロパティを実装します。  
  
 メソッドとプロパティ、パラメーター化されたプロパティと同様も使用できるパラメーターの数に制限があります。 パラメーター化されたプロパティは、の場合は、制限は、15 個のパラメーター (1 つのパラメーター プロパティの値を格納するために予約されています) とは。  
  
 次の手順では、整数の 2 次元の配列としてアクセス可能な配列と呼ばれる、パラメーター化されたプロパティを追加します。  
  
#### <a name="to-add-a-parameterized-property-using-the-add-property-wizard"></a>プロパティの追加ウィザードを使用してパラメーター化されたプロパティを追加するには  
  
1.  コントロールのプロジェクトを読み込みます。  
  
2.  [クラス ビュー] で、コントロールのライブラリ ノードを展開します。  
  
3.  コントロールのインターフェイス ノード (ライブラリ ノードの 2 番目のノード) を右クリックし、ショートカット メニューを開きます。  
  
4.  ショートカット メニューから **[追加]** をクリックし、**プロパティの追加**です。  
  
5.  **プロパティ名**ボックスに、入力`Array`です。  
  
6.  **プロパティの型**ボックスで、**短い**です。  
  
7.  **実装**型をクリックして**Get/set メソッド**です。  
  
8.  **Get 関数**と**設定関数**ボックス、Get と Set 関数に一意の名前を入力するか、既定の名前を受け入れます。  
  
9. という名前のパラメーターを追加`row`(型`short`) を使用して、**パラメーター名**と**パラメーターの型**コントロール。  
  
10. 呼ばれる 2 番目のパラメーターを追加`column`(型`short`)。  
  
11. **[完了]** をクリックします。  
  
### <a name="changes-made-by-the-add-property-wizard"></a>によって行われた変更によって、プロパティの追加ウィザード  
 プロパティの追加ウィザードによってコントロール クラスのヘッダーを変更、カスタム プロパティを追加するときに (です。H) と実装 (です。CPP) ファイル。  
  
 次の行は、コントロール クラスに追加されます。H ファイル:  
  
 [!code-cpp[NVC_MFC_AxUI#35](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_2.h)]  
  
 このコードと呼ばれる 2 つの関数を宣言して`GetArray`と`SetArray`プロパティにアクセスするときに、特定の行と列を要求するユーザーを許可します。  
  
 プロパティの追加ウィザードがさらに、次の行をコントロールのコントロール クラスの実装にあるディスパッチ マップに追加 (です。Cpp):  
  
 [!code-cpp[NVC_MFC_AxUI#36](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_3.cpp)]  
  
 実装では、最後に、`GetArray`と`SetArray`関数がの末尾に追加され、します。CPP ファイルです。 ほとんどの場合では、プロパティの値を返す Get 関数を変更します。 Set 関数には、通常の前に、またはプロパティの変更後、実行するコードが含まれます。  
  
 このプロパティを有効にするを型のコントロール クラスの 2 次元配列のメンバー変数を宣言します**短い**、パラメーター化されたプロパティの値を格納します。 パラメーターが示すとおりに適切な行と列に格納された値を返す Get 関数を変更し、行と列パラメーターによって参照される値を更新するセット関数を変更します。  
  
##  <a name="_core_handling_errors_in_your_activex_control"></a> ActiveX コントロールでのエラーを処理  
 コントロール内のエラー状態が発生した場合は、コントロールのコンテナーに、エラーを報告する必要があります。 エラーが発生した状況に応じて、エラーの報告の次の 2 つの方法はあります。 内のプロパティの取得エラーが発生した場合、または関数を OLE オートメーション メソッドの実装、内でコントロールを呼び出す必要がありますまたは[COleControl::ThrowError](../mfc/reference/colecontrol-class.md#throwerror)、そのシグナル コントロールことをユーザーにエラーが発生しました。 その他の任意の時にエラーが発生する場合、コントロールを呼び出す必要があります[COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror)、株価のエラー イベントが発生します。  
  
 発生したエラーの種類を示すために、コントロールがエラー コードを渡す必要があります`ThrowError`または`FireError`です。 エラー コードは、OLE ステータス コードは、32 ビット値です。 可能であれば、として使用で定義されたコードの標準セットからエラー コードを選択します。H ヘッダー ファイルです。 次の表は、これらのコードをまとめたものです。  
  
### <a name="activex-control-error-codes"></a>ActiveX コントロール エラー コード  
  
|Error|説明|  
|-----------|-----------------|  
|**CTL_E_ILLEGALFUNCTIONCALL**|無効な関数呼び出し|  
|**CTL_E_OVERFLOW**|オーバーフロー|  
|**CTL_E_OUTOFMEMORY**|メモリ不足|  
|**CTL_E_DIVISIONBYZERO**|0 による除算です。|  
|**CTL_E_OUTOFSTRINGSPACE**|文字列スペースが不足しています|  
|**CTL_E_OUTOFSTACKSPACE**|スタック領域不足|  
|**CTL_E_BADFILENAMEORNUMBER**|ファイル名または番号が正しくありません。|  
|**CTL_E_FILENOTFOUND**|ファイルが見つかりません。|  
|**CTL_E_BADFILEMODE**|ファイル モードが正しくありません。|  
|**CTL_E_FILEALREADYOPEN**|ファイルは既に開かれています。|  
|**CTL_E_DEVICEIOERROR**|デバイス I/O エラーです。|  
|**CTL_E_FILEALREADYEXISTS**|ファイルは既に存在します|  
|**CTL_E_BADRECORDLENGTH**|レコード長が正しくありません。|  
|**CTL_E_DISKFULL**|ディスクがいっぱいです。|  
|**CTL_E_BADRECORDNUMBER**|レコード番号が正しくありません|  
|**CTL_E_BADFILENAME**|不適切なファイル名|  
|**CTL_E_TOOMANYFILES**|ファイルが多すぎます。|  
|**CTL_E_DEVICEUNAVAILABLE**|デバイスが準備されていません|  
|**CTL_E_PERMISSIONDENIED**|アクセス許可は拒否されました|  
|**CTL_E_DISKNOTREADY**|ディスクが準備されていません|  
|**CTL_E_PATHFILEACCESSERROR**|パス/ファイル アクセス エラー|  
|**CTL_E_PATHNOTFOUND**|パスが見つかりません。|  
|**CTL_E_INVALIDPATTERNSTRING**|正しくないパターン文字列|  
|**CTL_E_INVALIDUSEOFNULL**|無効な NULL の使用|  
|**CTL_E_INVALIDFILEFORMAT**|ファイル形式が無効|  
|**CTL_E_INVALIDPROPERTYVALUE**|無効なプロパティ値|  
|**CTL_E_INVALIDPROPERTYARRAYINDEX**|無効なプロパティの配列のインデックス|  
|**CTL_E_SETNOTSUPPORTEDATRUNTIME**|Set は実行時にはサポートされません|  
|**CTL_E_SETNOTSUPPORTED**|Set はサポートされません。読み取り専用のプロパティです。|  
|**CTL_E_NEEDPROPERTYARRAYINDEX**|プロパティ配列のインデックスが必要です。|  
|**CTL_E_SETNOTPERMITTED**|Set は使用できません|  
|**CTL_E_GETNOTSUPPORTEDATRUNTIME**|Get は実行時にはサポートされません|  
|**CTL_E_GETNOTSUPPORTED**|Get はサポートされません。書き込み専用のプロパティです|  
|**CTL_E_PROPERTYNOTFOUND**|プロパティが見つかりません。|  
|**CTL_E_INVALIDCLIPBOARDFORMAT**|無効なクリップボード形式|  
|**CTL_E_INVALIDPICTURE**|無効な画像|  
|**CTL_E_PRINTERERROR**|プリンター エラーです|  
|**CTL_E_CANTSAVEFILETOTEMP**|ファイルを TEMP に保存することはできません。|  
|**CTL_E_SEARCHTEXTNOTFOUND**|検索文字列が見つかりませんでした|  
|**CTL_E_REPLACEMENTSTOOLONG**|置換後の文字列が長すぎます|  
  
 必要に応じて、使用して、 **CUSTOM_CTL_SCODE**マクロで説明されていない条件のいずれかの標準的なコードでのカスタム エラー コードを定義します。 このマクロのパラメーターが 1000 の間の整数にする必要があります、32767 です。 例えば:  
  
 [!code-cpp[NVC_MFC_AxUI#37](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_4.cpp)]  
  
 VBX の既存のコントロールを置換する ActiveX コントロールを作成する場合は、同じ数値と共に VBX コントロールは、エラー コードに互換性があることを確認してください。 を使用して、ActiveX コントロール エラー コードを定義します。  
  
##  <a name="_core_handling_special_keys_in_your_control"></a> コントロール内の特殊なキーの処理  
 場合によっては特別な方法で処理を特定のキーストロークの組み合わせにすることがあります。ときに、方向を挿入複数行のテキストで、ENTER キーが押されたときに、新しい行のボックス コントロールまたは編集の間を移動したりコントロールなど、押されたキーします。  
  
 場合は、ActiveX コントロールの基底クラスが`COleControl`、オーバーライドすることができます[cwnd::pretranslatemessage](../mfc/reference/cwnd-class.md#pretranslatemessage)コンテナーがそれらを処理する前にメッセージを処理します。 この手法を使用して場合、常に返します**TRUE**のオーバーライドで、メッセージを処理する場合`PreTranslateMessage`です。  
  
 次のコード例では、方向キーに関連するすべてのメッセージの処理の方法を示します。  
  
 [!code-cpp[NVC_MFC_AxUI#38](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_5.cpp)]  
  
 ActiveX コントロールのキーボード インターフェイスを処理する方法の詳細については、ActiveX SDK のマニュアルを参照してください。  
  
##  <a name="_core_accessing_dialog_controls_that_are_invisible_at_run_time"></a> 実行時に表示されないダイアログ コントロールへのアクセス  
 ユーザー インターフェイスがない実行時に表示されないダイアログ コントロールを作成することができます。 ActiveX コントロールの実行時にダイアログ ボックスを使用して、非表示を追加する場合[:getdlgitem](../mfc/reference/cwnd-class.md#getdlgitem)コントロールにアクセスするにはコントロールが正しく動作しません。 代わりに、コントロールを表すオブジェクトを取得するのに、次の手法のいずれかを使用する必要があります。  
  
-   追加のメンバー変数ウィザードを使用して選択**コントロール変数**し、コントロールの id。 メンバー変数の名前を入力し、コントロールのラッパー クラスを選択、**コントロール型**です。  
  
     - または -  
  
-   ダイアログの項目として、ローカル変数とサブクラスを宣言します。 次のようなコードを挿入 (`CMyCtrl`ラッパー クラスは、`IDC_MYCTRL1`コントロールの id を指定)。  
  
     [!code-cpp[NVC_MFC_AxCont#19](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_6.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)

