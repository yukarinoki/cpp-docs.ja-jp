---
title: キーボードとマウスのカスタマイズ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- customizations [MFC], keyboard and mouse (MFC Extensions)
- keyboard and mouse customizations (MFC Extensions)
ms.assetid: 1f789f1b-5f2e-4b11-b974-e3e2a2e49d82
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8fda670198dd9bd03a6d944ce4db70542926bf41
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931581"
---
# <a name="keyboard-and-mouse-customization"></a>キーボードとマウスのカスタマイズ
MFC は、キーボードとマウス入力の処理方法をカスタマイズする、アプリケーションのユーザーに許可します。 ユーザーは、コマンドをキーボード ショートカットを割り当てることによって、キーボード入力をカスタマイズできます。 ユーザーは、ユーザーがアプリケーションの特定のウィンドウ内をダブルクリックしたときに実行されるコマンドを選択してもマウス入力をカスタマイズできます。 このトピックでは、アプリケーションの入力をカスタマイズする方法について説明します。  
  
 **カスタマイズ**ダイアログ ボックスで、ユーザーは、マウスとキーボードのカスタム コントロールを変更できます。 このダイアログ ボックスを表示する、ユーザーのポイントを**カスタマイズ**上、**ビュー**メニューとし、クリック**ツールバーとドッキング ウィンドウ**します。 ダイアログ ボックスで、ユーザーがクリックするか、**キーボード** タブまたは**マウス**タブです。  
  
## <a name="keyboard-customization"></a>キーボードのカスタマイズ  
 次の図は、**キーボード**のタブ、**カスタマイズ** ダイアログ ボックス。  
  
 ![[カスタマイズ] ダイアログ ボックスで [キーボード] タブ](../mfc/media/mfcnextkeyboardtab.png "mfcnextkeyboardtab")  
キーボードのカスタマイズタブ  
  
 ユーザーは、1 つまたは複数のキーボード ショートカットをコマンドに割り当てる [キーボード] タブと対話します。 タブの左側にある、使用できるコマンドが表示されます。ユーザーは、メニューから使用可能なコマンドを選択できます。 メニュー コマンドだけは、キーボード ショートカットを関連付けることができます。 ユーザーは新しいショートカットが入力した後、**割り当てる**ボタンが有効になります。 ユーザーには、このボタンがクリックすると、アプリケーションは、選択したコマンドをそのショートカット キーに関連付けます。  
  
 現在割り当てられているショートカット キーのすべては、右側の列のリスト ボックスに表示されます。 ユーザーも個々 のショートカット キーを選択し、それらを削除したり、アプリケーションのすべてのマッピングをリセットできます。  
  
 作成する必要があります、アプリケーションでこのようなカスタマイズをサポートする場合、 [CKeyboardManager](../mfc/reference/ckeyboardmanager-class.md)オブジェクト。 作成する、`CKeyboardManager`オブジェクト、関数を呼び出す[CWinAppEx::InitKeyboardManager](../mfc/reference/cwinappex-class.md#initkeyboardmanager)です。 このメソッドは、作成し、キーボードのマネージャーを初期化します。 を作成する場合、キーボード manager 手動でも呼び出す必要があります`CWinAppEx::InitKeyboardManager`を初期化します。  
  
 アプリケーションを作成するウィザードを使用する場合、ウィザードはキーボード マネージャーを初期化します。 フレームワークは、追加、アプリケーションは、キーボードのマネージャーを初期化した後、**キーボード**タブ、**カスタマイズ**ダイアログ ボックス。  
  
## <a name="mouse-customization"></a>マウスのカスタマイズ  
 次の図は、**マウス**のタブ、**カスタマイズ** ダイアログ ボックス。  
  
 ![マウスタブ、[カスタマイズ] ダイアログ ボックスで](../mfc/media/mfcnextmousetab.png "mfcnextmousetab")  
マウスのカスタマイズタブ  
  
 メニューを割り当てるには、このタブで、ユーザーが操作するコマンドをマウスのダブルクリック操作します。 ユーザーは、ウィンドウの左側からビューを選択し、右側にあるコントロールを使用して、コマンド、ダブルクリック アクションと関連付けます。 ユーザー後がクリックした**閉じる**ユーザーがビューの任意の場所をダブルクリックしたときに、アプリケーションが関連付けられているコマンドを実行します。  
  
 既定では、マウスのカスタマイズは無効、ウィザードを使用してアプリケーションを作成する場合です。  
  
#### <a name="to-enable-mouse-customization"></a>マウスのカスタマイズを有効にするには  
  
1.  初期化、 [CMouseManager](../mfc/reference/cmousemanager-class.md)呼び出して[CWinAppEx::InitMouseManager](../mfc/reference/cwinappex-class.md#initmousemanager)です。  
  
2.  使用して、マウスのマネージャーへのポインターを取得[CWinAppEx::GetMouseManager](../mfc/reference/cwinappex-class.md#getmousemanager)です。  
  
3.  使用して、マウスのマネージャーにビューを追加、 [CMouseManager::AddView](../mfc/reference/cmousemanager-class.md#addview)メソッドです。 これは、マウス マネージャーに追加するすべてのビューに対して行います。  
  
 フレームワークは、追加、アプリケーションは、マウス マネージャーを初期化した後、**マウス**タブ、**カスタマイズ**ダイアログ ボックス。 すべてのビューを追加しないと場合、タブにアクセス、ハンドルされない例外が発生します。 ビューの一覧を作成した後、**マウス**タブは、ユーザーに使用できます。  
  
 マウス マネージャーに新しいビューを追加するときに指定した一意の id。 ウィンドウをマウスのカスタマイズをサポートする場合は、WM_LBUTTONDBLCLICK メッセージと呼び出しを処理する必要があります、 [CWinAppEx::OnViewDoubleClick](../mfc/reference/cwinappex-class.md#onviewdoubleclick)関数。 この関数を呼び出すときに、そのウィンドウの ID パラメーターのいずれかです。 数字の ID、およびそれらに関連付けられたオブジェクトを追跡するプログラマの責任においてすることをお勧めします。  
  
## <a name="security-concerns"></a>セキュリティに関する注意事項  
 」の説明に従って[ユーザー定義のツール](../mfc/user-defined-tools.md)ユーザーは、ツールのユーザー定義の ID をダブルクリック イベントに関連付けることができます。 ユーザーをダブルクリックすると、ビュー、アプリケーションが関連付けられている ID と一致するユーザー ツールの検索します。 アプリケーションには、一致するツールが見つかると、ツールを実行します。 一致するツールが見つからない場合は、ダブルクリックされたビューに ID を持つ WM_COMMAND メッセージを送信します。  
  
 カスタマイズした設定は、レジストリに格納されます。 レジストリを編集して、攻撃者は任意のコマンドを使用して有効なユーザー ツールの ID を置き換えることができます。 ユーザーをダブルクリックすると、ビュー、ビューは、攻撃者が植えたのコマンドを処理します。 これにより、予期しないと危険性のある動作が発生する可能性があります。  
  
 さらに、この種の攻撃は、ユーザー インターフェイスの保護をバイパスすることができます。 たとえば、アプリケーションに印刷を無効になっているとします。 つまり、そのユーザー インターフェイスで、**印刷**メニューおよびボタンは使用できません。 通常これは印刷からアプリケーションを防止します。 攻撃者が、レジストリを編集した場合、ユーザーでしたようになりましたでした送信、print コマンド、ビューをダブルクリックして直接使用できるユーザー インターフェイス要素をバイパスします。  
  
 この種の攻撃を防ぐが実行される前に、コマンドが有効であることを確認するアプリケーションのコマンド ハンドラーにコードを追加します。 ユーザー インターフェイスでコマンドがアプリケーションに送信されないようにするために依存しません。  
  
## <a name="see-also"></a>関連項目  
 [MFC のカスタマイズ](../mfc/customization-for-mfc.md)   
 [CKeyboardManager クラス](../mfc/reference/ckeyboardmanager-class.md)   
 [CMouseManager クラス](../mfc/reference/cmousemanager-class.md)   
 [カスタマイズによるセキュリティへの影響](../mfc/security-implications-of-customization.md)

