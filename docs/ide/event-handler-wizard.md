---
title: イベント ハンドラー ウィザード | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.eventhandler.overview
dev_langs:
- C++
helpviewer_keywords:
- Event Handler Wizard [C++]
ms.assetid: af8e1835-94b1-4d9a-b353-c519e011d3a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 544ce4cd0f4ed9a7f3592e5ec1691fb3734b8772
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33340009"
---
# <a name="event-handler-wizard"></a>イベント ハンドラー ウィザード
このウィザードは、ダイアログ ボックス コントロール用のイベント ハンドラーをクラスに追加します。 [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)からイベント ハンドラーを追加する場合は、ダイアログ ボックスを実装するクラスに対してのみ追加できます。 詳しくは、「[ダイアログ ボックス コントロールへのイベント ハンドラーの追加](../windows/adding-event-handlers-for-dialog-box-controls.md)」をご覧ください。  
  
 **コマンド名**  
 選ばれているコントロールを示します。このコントロールにイベント ハンドラーが追加されます。 このボックスは変更できません。  
  
 **メッセージ型**  
 選ばれているコントロールで現在使用可能なメッセージ ハンドラーの一覧が表示されます。  
  
 **関数ハンドラー名**  
 イベントを処理するために追加される関数の名前が表示されます。 既定の名前は、メッセージ型とコマンドに基づき、先頭に "On" が付加されます。 たとえば、`IDC_BUTTON1` という名前のボタンでメッセージ型が `BN_CLICKED` の場合、関数ハンドラーの名前は `OnBnClickedButton1` になります。  
  
 **クラスの一覧**  
 イベント ハンドラーを追加できるクラスが表示されます。 選ばれているダイアログ ボックスのクラスは、赤で表示されます。  
  
 **ハンドラーの説明**  
 **[メッセージ型]** ボックスで選ばれている項目の説明が表示されます。 このボックスは変更できません。  
  
 **追加と編集**  
 選択したクラスまたはオブジェクトにメッセージ ハンドラーを追加した後、テキスト エディターで新しい関数が開き、コントロール通知ハンドラー コードを追加できます。  
  
 **コードの編集**  
 選択した既存の関数がテキスト エディターで開き、コントロール通知ハンドラー コードを追加または編集できます。  
  
## <a name="see-also"></a>参照  
 [イベント ハンドラーの追加](../ide/adding-an-event-handler-visual-cpp.md)