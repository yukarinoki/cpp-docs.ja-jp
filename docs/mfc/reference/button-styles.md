---
title: ボタン スタイル |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- BS_DEFPUSHBUTTON
- BS_NOTIFY
- BS_MULTILINE
- BS_AUTOCHECKBOX
- BS_3STATE
- BS_BITMAP
- BS_TOP
- BS_PUSHBUTTON
- BS_PUSHLIKE
- BS_AUTO3STATE
- BS_CHECKBOX
- BS_AUTORADIOBUTTON
- BS_RADIOBUTTON
- BS_OWNERDRAW
- BS_LEFT
- BS_USERBUTTON
- BS_RIGHTBUTTON
- BS_RIGHT
- BS_LEFTTEXT
- BS_TEXT
- BS_BOTTOM
- BS_GROUPBOX
- BS_FLAT
- BS_VCENTER
- BS_ICON
- BS_CENTER
dev_langs:
- C++
helpviewer_keywords:
- BS_NOTIFY constant [MFC]
- BS_RIGHTBUTTON constant [MFC]
- styles [MFC], button objects
- BS_USERBUTTON constant [MFC]
- BS_VCENTER constant [MFC]
- BS_PUSHLIKE constant [MFC]
- BS_RADIOBUTTON constant [MFC]
- BS_PUSHBUTTON constant [MFC]
- BS_DEFPUSHBUTTON constant [MFC]
- BS_LEFTTEXT constant [MFC]
- button objects (CButton), button styles
- BS_AUTO3STATE constant [MFC]
- BS_3STATE constant [MFC]
- BS_OWNERDRAW constant [MFC]
- BS_AUTORADIOBUTTON constant [MFC]
- BS_GROUPBOX constant [MFC]
- BS_BITMAP constant [MFC]
- BS_CENTER constant [MFC]
- BS_MULTILINE constant [MFC]
- BS_BOTTOM constant [MFC]
- BS_FLAT constant [MFC]
- BS_AUTOCHECKBOX constant [MFC]
- BS_RIGHT constant [MFC]
- BS_CHECKBOX constant [MFC]
- BS_LEFT constant [MFC]
- BS_ICON constant [MFC]
- BS_TOP constant [MFC]
- BS_TEXT constant
ms.assetid: 41206f72-2b92-4250-ae32-31184046402f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3ec945c95b81570e52cca03ed4e52355350d8121
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="button-styles"></a>ボタン スタイル
ここでは、ボタンの種類とスタイルについて説明します。  
  
## <a name="button-types"></a>ボタンの種類  
 次の表は、ボタンの種類の一覧です。 次のいずれかを必要に応じて選択できます。 ボタンの種類を指定しない場合、既定値は`BS_PUSHBUTTON`します。  
  
|型|説明|  
|----------|-----------------|  
|`BS_3STATE`|次の 3 つの状態を持つチェック ボックス ボタンを作成します。 `BST_CHECKED`、 `BST_INDETERMINATE`、および`BST_UNCHECKED`です。 このボタンをクリックすると、オーナー ウィンドウに `BN_CLICKED` 通知が送信されますが、ボタンの状態は変更されません。 既定では、関連付けられたテキストはチェック ボックスの右側に表示されます。 チェック ボックスの左側にテキストを表示するには、`BS_LEFTTEXT` スタイルまたは `BS_RIGHTBUTTON` スタイルを使用します。|  
|`BS_AUTO3STATE`|次の 3 つの状態を持つチェック ボックス ボタンを作成します。 `BST_CHECKED`、 `BST_INDETERMINATE`、および`BST_UNCHECKED`です。 このボタンをクリックすると、オーナー ウィンドウに `BN_CLICKED` 通知が送信され、ボタンの状態が変更されます。 ボタンの状態は、`BST_CHECKED`、`BST_INDETERMINATE`、`BST_UNCHECKED` の順序で循環します。 既定では、関連付けられたテキストはチェック ボックスの右側に表示されます。 チェック ボックスの左側にテキストを表示するには、`BS_LEFTTEXT` スタイルまたは `BS_RIGHTBUTTON` スタイルを使用します。|  
|`BS_AUTOCHECKBOX`|2 つの状態を持つチェック ボックス ボタンを作成します。このボタンには、`BST_CHECKED` と `BST_UNCHECKED` の状態があります。 このボタンをクリックすると、オーナー ウィンドウに `BN_CLICKED` 通知が送信され、ボタンの状態が変更されます。 既定では、関連付けられたテキストはチェック ボックスの右側に表示されます。 チェック ボックスの左側にテキストを表示するには、`BS_LEFTTEXT` スタイルまたは `BS_RIGHTBUTTON` スタイルを使用します。|  
|`BS_AUTORADIOBUTTON`|2 つの状態を持つオプション ボタンを作成します。このボタンには、`BST_CHECKED` と `BST_UNCHECKED` の状態があります。 通常、オプション ボタンはグループで使用します。各グループで一度に選択できるオプションは 1 つだけです。 このボタンをクリックすると、`BN_CLICKED` 通知がオーナー ウィンドウに送信され、クリックしたオプション ボタンの状態が `BST_CHECKED` に設定されて、そのボタン グループに含まれる他のすべてのオプション ボタンの状態が `BST_UNCHECKED` に設定されます。 既定では、関連付けられたテキストはオプション ボタンの右側に表示されます。 オプション ボタンの左側にテキストを表示するには、`BS_LEFTTEXT` スタイルまたは `BS_RIGHTBUTTON` スタイルを使用します。|  
|`BS_CHECKBOX`|2 つの状態を持つチェック ボックス ボタンを作成します。このボタンには、`BST_CHECKED` と `BST_UNCHECKED` の状態があります。 このボタンをクリックすると、オーナー ウィンドウに `BN_CLICKED` 通知が送信されますが、ボタンの状態は変更されません。 既定では、関連付けられたテキストはチェック ボックスの右側に表示されます。 チェック ボックスの左側にテキストを表示するには、`BS_LEFTTEXT` スタイルまたは `BS_RIGHTBUTTON` スタイルを使用します。|  
|`BS_COMMANDLINK`|コマンド リンク ボタンを作成します。 コマンド リンク ボタンは [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] に固有のコマンド ボタンで、メイン テキストの左側に緑の矢印が表示され、メイン テキストの下に注釈が表示されます。 注意のテキストを使用して、設定することができます[CButton::SetNote](../../mfc/reference/cbutton-class.md#setnote)です。|  
|`BS_DEFCOMMANDLINK`|コマンド リンク ボタンを作成します。 コマンド リンク ボタンは [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] に固有のコマンド ボタンで、メイン テキストの左側に緑の矢印が表示され、メイン テキストの下に注釈が表示されます。 注意のテキストを使用して、設定することができます[CButton::SetNote](../../mfc/reference/cbutton-class.md#setnote)です。 このボタンがダイアログ ボックス内にある場合、ボタンに入力フォーカスがなくても、Enter キーを押すとダイアログ ボックスに `BN_CLICKED` 通知が送信されます。|  
|`BS_DEFPUSHBUTTON`|境界線が黒くて太いコマンド ボタンを作成します。 このボタンがダイアログ ボックス内にある場合、ボタンに入力フォーカスがなくても、Enter キーを押すとダイアログ ボックスに `BN_CLICKED` 通知が送信されます。|  
|`BS_DEFSPLITBUTTON`|分割ボタンを作成します。 分割ボタンは [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] に固有のコマンド ボタンで、ボタンとドロップダウン矢印が並んで表示されます。 ボタンをクリックすると、既定のコマンドが実行されます。 ドロップダウン矢印をクリックすると、追加のコマンドのメニューが表示されます。 この分割ボタンがダイアログ ボックス内にある場合、ボタンに入力フォーカスがなくても、Enter キーを押すとダイアログ ボックスに `BN_CLICKED` 通知が送信されます。|  
|`BS_GROUPBOX`|他のボタンをグループ化する四角形を作成します。 このスタイルに関連付けられたテキストは、この四角形の左上隅に表示されます。|  
|`BS_OWNERDRAW`|オーナー描画ボタンを作成します。 ボタンの外観が変更されると、フレームワークは `DrawItem` メソッドを呼び出します。 `CBitmapButton` クラスを使用するときは、このスタイルを設定する必要があります。|  
|`BS_PUSHBUTTON`|コマンド ボタンを作成します。ユーザーがボタンをクリックすると、オーナー ウィンドウに `BN_CLICKED` 通知が送信されます。|  
|`BS_RADIOBUTTON`|2 つの状態を持つオプション ボタンを作成します。このボタンには、`BST_CHECKED` と `BST_UNCHECKED` の状態があります。 通常、オプション ボタンはグループで使用します。各グループで一度に選択できるオプションは 1 つだけです。 このボタンをクリックすると、オーナー ウィンドウに `BN_CLICKED` 通知が送信されますが、グループ内のどのボタンの状態も自動的には変更されません。 既定では、関連付けられたテキストはオプション ボタンの右側に表示されます。 オプション ボタンの左側にテキストを表示するには、`BS_LEFTTEXT` スタイルまたは `BS_RIGHTBUTTON` スタイルを使用します。|  
|`BS_SPLITBUTTON`|分割ボタンを作成します。 分割ボタンは [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] に固有のコマンド ボタンで、ボタンとドロップダウン矢印が並んで表示されます。 ボタンをクリックすると、既定のコマンドが実行されます。 ドロップダウン矢印をクリックすると、追加のコマンドのメニューが表示されます。|  
|`BS_USERBUTTON`|現在では使用されていないスタイルですが、16 ビット バージョンの Windows との下位互換性のために残されています。 Win32 ベースのアプリケーションでは、このスタイルではなく `BS_OWNERDRAW` を使用してください。|  
  
## <a name="radio-button-and-check-box-styles"></a>オプション ボタンおよびチェック ボックスのスタイル  
 次の表は、オプション ボタンとチェック ボックスに固有のスタイルの一覧です。 これらのスタイルは、オプション ボタンおよびチェック ボックス以外のボタンの種類では無視されます。 次の中から 1 つ以上を必要に応じて選択できます。  
  
|スタイル|説明|  
|-----------|-----------------|  
|`BS_LEFTTEXT`|オプション ボタンまたはチェック ボックスのスタイルと組み合わせて指定すると、オプション ボタンまたはチェック ボックスの左側にテキストが表示されます。|  
|`BS_RIGHTBUTTON`|オプション ボタンまたはチェック ボックスのスタイルと組み合わせて指定すると、オプション ボタンまたはチェック ボックスの左側にテキストが表示されます。 このスタイルは `BS_LEFTTEXT` スタイルと同じです。|  
|`BS_PUSHLIKE`|チェック ボックスまたはオプション ボタンの外観と動作をコマンド ボタンのようにします。 ボタンは、ボタンの状態が `BST_CHECKED` の場合は押された状態で表示され、ボタンの状態が `BST_INDETERMINATE` の場合は押された状態で淡色表示され、ボタンの状態が `BST_UNCHECKED` の場合は押されていない状態で表示されます。|  
  
## <a name="text-alignment-styles"></a>テキストの配置スタイル  
 次の表は、水平方向と垂直方向のテキストの配置オプションの一覧です。 次のいずれかを必要に応じて選択できます。  
  
|スタイル|説明|  
|-----------|-----------------|  
|`BS_LEFT`|ボタンの四角形の内部にテキストを左寄せで配置します。 ただし、`BS_RIGHTBUTTON` スタイルが適用されていないチェック ボックスまたはオプション ボタンの場合、テキストはそのチェック ボックスまたはオプション ボタンの右側に、左寄せで配置されます。|  
|`BS_RIGHT`|ボタンの四角形の内部にテキストを右寄せで配置します。 ただし、`BS_RIGHTBUTTON` スタイルが適用されていないチェック ボックスまたはオプション ボタンの場合、テキストはそのチェック ボックスまたはオプション ボタンの右側に、右寄せで配置されます。|  
|`BS_CENTER`|ボタンの四角形内でテキストを水平方向に中央揃えで配置します。|  
|`BS_TOP`|ボタンの四角形の上部にテキストを配置します。|  
|`BS_BOTTOM`|ボタンの四角形の下部にテキストを配置します。|  
|`BS_VCENTER`|ボタンの四角形内でテキストを垂直方向に中央揃えで配置します。|  
  
## <a name="button-content-options"></a>ボタンの内容に関するオプション  
 次の表は、ボタンに表示する内容を指定するオプションの一覧です。 テキストしか表示されないボタンの種類では、これらのスタイルは無視されます。 次のいずれかを必要に応じて選択できます。  
  
|スタイル|説明|  
|-----------|-----------------|  
|`BS_BITMAP`|ボタンにビットマップを表示することを指定します。|  
|`BS_ICON`|ボタンにアイコンを表示することを指定します。|  
|`BS_TEXT`|ボタンにテキストを表示することを指定します。|  
  
## <a name="other-options"></a>その他のオプション  
 次の表は、任意のボタンの種類で使用できるその他のオプションの一覧です。 次の中から 1 つ以上を必要に応じて選択できます。  
  
|スタイル|説明|  
|-----------|-----------------|  
|`BS_FLAT`|ボタンが 2 次元であり、3 次元イメージを作成するための既定の網かけは描画しないように指定します。|  
|`BS_MULTILINE`|文字列が長すぎてボタンの四角形の内部に 1 行で収まらない場合は、ボタン テキストを複数行に折り返します。|  
|`BS_NOTIFY`|ボタンが `BN_DBLCLK`、`BN_KILLFOCUS`、`BN_SETFOCUS` の各通知メッセージを親ウィンドウに送信できるようになります。 ボタンは、このスタイルが指定されているかどうかに関係なく、`BN_CLICKED` 通知を送信します。|  
  
## <a name="see-also"></a>関連項目  
 [MFC によって使用されているスタイル](../../mfc/reference/styles-used-by-mfc.md)   
 [CButton::Create](../../mfc/reference/cbutton-class.md#create) [ボタン スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775951)   



