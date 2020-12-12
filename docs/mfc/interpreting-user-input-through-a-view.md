---
description: 詳細については、「ビューを使用したユーザー入力の解釈」を参照してください。
title: ビューを経由したユーザー入力の解釈
ms.date: 11/04/2016
helpviewer_keywords:
- interpreting user input through views [MFC]
- views [MFC], user interface and input
- input [MFC], view class [MFC]
- CView class [MFC], interpreting user input
- user input [MFC], interpreting through view class [MFC]
ms.assetid: f0302a70-661f-4781-8fe7-78f082bef2a5
ms.openlocfilehash: f3442a13bc60b7424840e23673806c1e5120c4ad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335829"
---
# <a name="interpreting-user-input-through-a-view"></a>ビューを経由したユーザー入力の解釈

ビューのその他のメンバー関数は、すべてのユーザー入力を処理して解釈します。 通常は、次の処理を行うために、ビュークラスでメッセージハンドラーのメンバー関数を定義します。

- マウスとキーボードの操作によって生成される Windows [メッセージ](messages.md) 。

- メニュー、ツールバーボタン、およびアクセラレータキーからの[コマンド](user-interface-objects-and-command-ids.md)です。

これらのメッセージハンドラーメンバー関数は、クリップボードとの間でのデータの移動を含む、データの入力、選択、または編集として、次のアクションを解釈します。

- マウスの動きとクリック、ドラッグ、ダブルクリック

- キーストローク

- メニュー コマンド

ビューが処理する Windows メッセージは、アプリケーションのニーズによって異なります。

[メッセージの処理とマッピングのトピック](message-handling-and-mapping.md) では、メニュー項目やその他のユーザーインターフェイスオブジェクトをコマンドに割り当てる方法と、コマンドをハンドラー関数にバインドする方法について説明します。 また、[メッセージの処理とマッピングのトピック](message-handling-and-mapping.md)では、MFC がコマンドをルーティングし、標準の Windows メッセージをそれらのハンドラーを含むオブジェクトに送信する方法についても説明します。

たとえば、アプリケーションでは、ビューにマウスの直接描画を実装することが必要になる場合があります。 Scribble サンプルは、WM_LBUTTONDOWN、WM_MOUSEMOVE、および WM_LBUTTONUP メッセージの処理方法を示しています。これらのメッセージは、それぞれ、直線セグメントの開始、続行、および終了のために行われます。 一方、ビュー内のマウスクリックを選択として解釈することが必要になる場合もあります。 ビューの `OnLButtonDown` ハンドラー関数は、ユーザーが描画または選択していたかどうかを判断します。 選択した場合、ハンドラーは、クリックがビュー内のオブジェクトの境界内にあるかどうかを判断し、存在する場合は、選択されたオブジェクトを表示するように表示を変更します。

また、ビューでは、[編集] メニューのメニューコマンドを使用して、クリップボードを使用して選択したデータを切り取り、コピー、貼り付け、または削除することもできます。 このようなハンドラーは、クラスのクリップボード関連のメンバー関数の一部を呼び出して、 `CWnd` 選択したデータ項目をクリップボードとの間で転送します。

## <a name="see-also"></a>関連項目

[ビューの使用](using-views.md)
