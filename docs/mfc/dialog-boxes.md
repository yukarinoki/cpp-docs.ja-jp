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
ms.openlocfilehash: da6a2eca7c2366e519b9bf2e809b042dc3ee2e50
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616869"
---
# <a name="dialog-boxes"></a>ダイアログ ボックス

Windows 用アプリケーションは、ダイアログボックスを通じてユーザーと頻繁に通信します。 クラス[CDialog](reference/cdialog-class.md)には、ダイアログボックスを管理するためのインターフェイスが用意されています。 Visual C++ ダイアログエディターを使用すると、ダイアログボックスのデザインやダイアログテンプレートリソースの作成が簡単になります。また、コードウィザードを使用すると、ダイアログボックス内のコントロールを初期化および検証したり、ユーザーが入力した値を収集したりできます。

ダイアログボックスには、次のようなコントロールがあります。

- エディットボックス、プッシュボタン、リストボックス、コンボボックス、ツリーコントロール、リストコントロール、進行状況インジケーターなどの Windows コモンコントロール。

- ActiveX コントロール。

- オーナー描画コントロール: ダイアログボックスでの描画を担当するコントロールです。

ほとんどのダイアログボックスはモーダルであり、プログラムの他の部分を使用する前に、ユーザーがダイアログボックスを閉じる必要があります。 ただし、ダイアログボックスが開いている間にユーザーが他のウィンドウを操作できるように、モードレスのダイアログボックスを作成することもできます。 MFC では、クラスを使用した両方の種類のダイアログボックスをサポートしてい `CDialog` ます。 コントロールは、ダイアログ[エディター](../windows/dialog-editor.md)で作成されたダイアログテンプレートリソースを使用して、配置および管理されます。

タブダイアログボックスとも呼ばれる[プロパティシート](property-sheets-mfc.md)は、ダイアログボックスのダイアログボックスコントロールの "ページ" を含むダイアログボックスです。 各ページの上部には、"タブ" というファイルフォルダーがあります。 タブをクリックすると、そのページがダイアログボックスの前に表示されます。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [例 : メニュー コマンドによるダイアログ ボックスの表示](example-displaying-a-dialog-box-via-a-menu-command.md)

- [フレームワークのダイアログボックスコンポーネント](dialog-box-components-in-the-framework.md)

- [モーダルとモードレスのダイアログ ボックス](modal-and-modeless-dialog-boxes.md)

- ダイアログボックスの[プロパティシートとプロパティページ](property-sheets-and-property-pages-mfc.md)

- [ダイアログ リソースの作成](creating-the-dialog-resource.md)

- [コードウィザードを使用したダイアログクラスの作成](creating-a-dialog-class-with-code-wizards.md)

- [MFC でのダイアログ ボックスの操作](life-cycle-of-a-dialog-box.md)

- [ダイアログデータエクスチェンジ (DDX) と検証 (DDV)](dialog-data-exchange-and-validation.md)

- [ダイアログ ボックスのコントロールへのタイプ セーフ アクセス](type-safe-access-to-controls-in-a-dialog-box.md)

- [Windows メッセージをクラスにマップする](mapping-windows-messages-to-your-class.md)

- [通常オーバーライドされるメンバー関数](commonly-overridden-member-functions.md)

- [通常追加されるメンバー関数](commonly-added-member-functions.md)

- [コモン ダイアログ クラス](common-dialog-classes.md)

- [ダイアログボックス (OLE の)](dialog-boxes-in-ole.md)

- ユーザーインターフェイスがダイアログボックスであるアプリケーションを作成する: [CMNCTRL1](../overview/visual-cpp-samples.md)または[CMNCTRL2](../overview/visual-cpp-samples.md)サンプルプログラムを参照してください。 このオプションは、アプリケーションウィザードにも用意されています。

- [サンプル](dialog-sample-list.md)

## <a name="see-also"></a>関連項目

[ユーザーインターフェイス要素](user-interface-elements-mfc.md)
