---
title: ダイアログ ボックス
ms.date: 11/04/2016
helpviewer_keywords:
- modeless dialog boxes [MFC], MFC dialog boxes
- MFC, dialog boxes
- modal dialog boxes [MFC], MFC dialog boxes
- CDialog class [MFC], MFC dialog boxes
- MFC dialog boxes
ms.assetid: e4feea1a-8360-4ccb-9b84-507f1ccd9ef3
ms.openlocfilehash: 32a8f8784459338131d4893f25d8798f8031b68b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62262633"
---
# <a name="dialog-boxes"></a>ダイアログ ボックス

Windows 用のアプリケーションは、ダイアログ ボックスを通じてユーザーと頻繁に通信します。 クラス[CDialog](../mfc/reference/cdialog-class.md)  ダイアログ ボックスを管理するには、Visual C ダイアログ エディター簡単にダイアログ ボックスを設計およびそのダイアログ テンプレート リソースを作成し、コード ウィザードの初期化中のプロセスを簡略化のインターフェイスを提供し、検証コントロールをダイアログ ボックスで、ユーザーが入力した値を収集しています。

ダイアログ ボックスにはなどのコントロールが含まれます。

- ボックス、プッシュ ボタン、リスト ボックス、コンボ ボックス、ツリー コントロール、リスト コントロール、および進行状況インジケーターなど、Windows のコモン コントロールが編集します。

- ActiveX コントロール。

- オーナー描画コントロール: ダイアログ ボックスを描画するために担当しているコントロール。

ほとんどのダイアログ ボックスは、ユーザーをプログラムの他の部分を使用する前に、ダイアログ ボックスを閉じる必要がありますがモーダルでは。 ユーザー ダイアログ ボックスが開いている間に他の windows で作業できるようにする、モードレス ダイアログ ボックスを作成することはできます。 MFC クラスを使用してダイアログ ボックスの両方の種類をサポートしている`CDialog`します。 コントロールの配置し、で作成された、ダイアログ テンプレート リソースを使用して管理、[ダイアログ エディター](../windows/dialog-editor.md)します。

[プロパティ シート](../mfc/property-sheets-mfc.md)とも呼ばれるタブ ダイアログ ボックス、ダイアログ ボックスの個別のコントロールの「ページ」を含むダイアログ ボックスします。 各ページでは、ファイル フォルダーの上部にある「タブ」があります。 タブをクリックしてダイアログ ボックスの前にそのページが表示されます。

## <a name="what-do-you-want-to-know-more-about"></a>方法については、するして操作を行います

- [例:メニュー コマンドによるダイアログ ボックスの表示](../mfc/example-displaying-a-dialog-box-via-a-menu-command.md)

- [フレームワークのダイアログ ボックス コンポーネント](../mfc/dialog-box-components-in-the-framework.md)

- [モーダルとモードレスのダイアログ ボックス](../mfc/modal-and-modeless-dialog-boxes.md)

- [プロパティ シートとプロパティ ページ](../mfc/property-sheets-and-property-pages-mfc.md) ダイアログ ボックス

- [ダイアログ リソースの作成](../mfc/creating-the-dialog-resource.md)

- [コード ウィザードによるダイアログ クラスの作成](../mfc/creating-a-dialog-class-with-code-wizards.md)

- [ダイアログ ボックスのライフ サイクル](../mfc/life-cycle-of-a-dialog-box.md)

- [ダイアログ データ エクス (チェンジ DDX) と検証 (DDV)](../mfc/dialog-data-exchange-and-validation.md)

- [ダイアログ ボックスのコントロールへのタイプ セーフ アクセス](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)

- [クラスに Windows メッセージの割り当てください。](../mfc/mapping-windows-messages-to-your-class.md)

- [通常オーバーライドされるメンバー関数](../mfc/commonly-overridden-member-functions.md)

- [通常追加されるメンバー関数](../mfc/commonly-added-member-functions.md)

- [コモン ダイアログ クラス](../mfc/common-dialog-classes.md)

- [OLE のダイアログ ボックス](../mfc/dialog-boxes-in-ole.md)

- ダイアログ ボックスのユーザー インターフェイスがアプリケーションを作成します。 を参照してください、 [CMNCTRL1](../overview/visual-cpp-samples.md)または[CMNCTRL2](../overview/visual-cpp-samples.md)サンプル プログラム。 アプリケーション ウィザードでは、このオプションも提供します。

- [サンプル](../mfc/dialog-sample-list.md)

## <a name="see-also"></a>関連項目

[ユーザー インターフェイス要素](../mfc/user-interface-elements-mfc.md)
