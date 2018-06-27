---
title: ユーザー定義ツール |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- user-defined tools (MFC Extensions)
ms.assetid: cb887421-78ce-4652-bc67-96a53984ccaa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4b78e9a4fefad884f4ac683cd0c7f18688a5bdfe
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36950815"
---
# <a name="user-defined-tools"></a>ユーザー定義のツール
MFC には、ユーザー定義のツールがサポートしています。 ユーザー定義のツールは、外部のユーザーが指定したプログラムを実行する特別なコマンドです。 カスタマイズ プロセスを使用して、ユーザー定義のツールを管理することができます。 アプリケーション オブジェクトを派生していない場合にこのプロセスを使用することはできませんただし、 [CWinAppEx クラス](../mfc/reference/cwinappex-class.md)です。 カスタマイズの詳細については、次を参照してください。 [MFC のカスタマイズ](../mfc/customization-for-mfc.md)です。  
  
 ユーザー定義のツールのサポートを有効にした場合、[カスタマイズ] ダイアログ ボックスに自動的が含まれています、**ツール**タブです。次の図は、**ツール**ページ。  
  
 ![ツールのタブ、[カスタマイズ] ダイアログ ボックスで](../mfc/media/custdialogboxtoolstab.png "custdialogboxtoolstab")  
カスタマイズ ダイアログ ボックスの ツール タブ  
  
## <a name="enabling-user-defined-tools-support"></a>ユーザー定義の有効化のツールのサポート  
 アプリケーションでユーザー定義のツールを有効にするを呼び出す[CWinAppEx::EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools)です。 ただし、この呼び出しのパラメーターとして使用するアプリケーションのリソース ファイルにいくつかの定数を定義する必要がありますまずします。  
  
 リソース エディターで、該当するコマンド ID を使用するコマンドをダミーを作成します。 次の例では使用`ID_TOOLS_ENTRY`とコマンド id。 このコマンド ID は、フレームワークがユーザー定義のツールを挿入する 1 つまたは複数のメニュー内の位置をマークします。  
  
 必要があります確保する一連の Id をユーザー定義のツールを表す文字列テーブルにします。 確保しておいた文字列の数は、ユーザーが定義できるユーザー ツールの最大数と同じです。 次の例では、これらの名前は`ID_USER_TOOL1`を通じて`ID_USER_TOOL10`です。  
  
 提案をツールとしてのディレクトリと呼び出される外部プログラムの引数を選択する際のユーザーに提供できます。 これを行うには、リソース エディターで 2 つのポップアップ メニューを作成します。 次の例でこれらの名前は`IDR_MENU_ARGS`と`IDR_MENU_DIRS`です。 これらのメニュー内の各コマンドには、アプリケーションの文字列テーブルに文字列を定義します。 文字列のリソース ID は、コマンド ID と一致する必要があります。  
  
 派生クラスを作成することもできます。 [CUserTool クラス](../mfc/reference/cusertool-class.md)を既定の実装を置き換えます。 これを行うには、対象となるのではなく、CWinAppEx::EnableUserTools の 4 番目のパラメーターとして、派生クラスのランタイム情報を渡す ([CUserTool クラス](../mfc/reference/cusertool-class.md))。  
  
 適切な定数を定義した後で呼び出す[CWinAppEx::EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools)をユーザー定義のツールを有効にします。  
  
 次のメソッド呼び出しは、これらの定数を使用する方法を示しています。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#1](../mfc/codesnippet/cpp/user-defined-tools_1.cpp)]  
  
 この例では、ツール タブに含まれます、**カスタマイズ** ダイアログ ボックス。 フレームワークは、コマンド ID に一致するコマンドを置き換えます`ID_TOOLS_ENTRY`ユーザーは、そのメニューを開くときに現在定義されているユーザー ツールのセットで任意のメニューにします。 コマンド Id`ID_USER_TOOL1`を通じて`ID_USER_TOOL10`ユーザー定義のツールを使用するために予約されています。 クラス[CUserTool クラス](../mfc/reference/cusertool-class.md)ユーザー ツールへの呼び出しを処理します。 ツール タブ、**カスタマイズ** ダイアログ ボックスに、メニューにアクセスする引数とディレクトリのエントリ フィールドの右側にあるボタンが用意されています**IDR_MENU_ARGS**と**IDR_MENU_DIRS**.ユーザーは、これらのメニューのいずれかのコマンドを選択するときに、フレームワーク文字列を追加、該当するテキスト ボックスに、リソースの ID を持つコマンド ID に等しい  
  
### <a name="including-predefined-tools"></a>定義済みのツールを含む  
 アプリケーションの起動時に一部のツールを事前に定義する場合は、オーバーライドする必要があります、 [CFrameWnd::LoadFrame](../mfc/reference/cframewnd-class.md#loadframe)アプリケーションのメイン ウィンドウのメソッドです。 そのメソッドでは、次の手順を実行する必要があります。  
  
##### <a name="to-add-new-tools-in-loadframe"></a>LoadFrame で新しいツールを追加するには  
  
1.  ポインターを取得、 [CUserToolsManager クラス](../mfc/reference/cusertoolsmanager-class.md)呼び出して[CWinAppEx::GetUserToolsManager](../mfc/reference/cwinappex-class.md#getusertoolsmanager)です。  
  
2.  作成するすべてのツールを呼び出して[CUserToolsManager::CreateNewTool](../mfc/reference/cusertoolsmanager-class.md#createnewtool)です。 このメソッドへのポインターを返します、 [CUserTool クラス](../mfc/reference/cusertool-class.md)オブジェクトし、ツールの内部コレクションに、新しく作成されたユーザー ツールを追加します。 派生クラスのランタイム情報を指定したかどうかは[CUserTool クラス](../mfc/reference/cusertool-class.md)の 4 番目のパラメーターとして[CWinAppEx::EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools)、 [CUserToolsManager::CreateNewTool](../mfc/reference/cusertoolsmanager-class.md#createnewtool)がインスタンス化され、代わりにそのクラスのインスタンスが返されます。  
  
3.  各ツールでは、設定のテキスト ラベルを設定して`CUserTool::m_strLabel`を呼び出して、コマンドを設定および`CUserTool::SetCommand`です。 既定の実装[CUserTool クラス](../mfc/reference/cusertool-class.md)への呼び出しで指定されているプログラムから使用可能なアイコンを自動的に取得`SetCommand`です。  
  
## <a name="see-also"></a>関連項目  
 [MFC のカスタマイズ](../mfc/customization-for-mfc.md)   
 [CUserTool クラス](../mfc/reference/cusertool-class.md)   
 [CUserToolsManager クラス](../mfc/reference/cusertoolsmanager-class.md)   
 [CWinAppEx クラス](../mfc/reference/cwinappex-class.md)




