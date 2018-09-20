---
title: フレームの Windows の破棄 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- PostNcDestroy
dev_langs:
- C++
helpviewer_keywords:
- Default method [MFC]
- DestroyWindow method [MFC]
- frame windows [MFC], destroying
- OnNcDestroy method, and frame windows
- document frame windows [MFC], destroying
- destroying frame windows
- MFC, frame windows
- windows [MFC], destroying
- OnClose method [MFC]
- PostNcDestroy method [MFC]
ms.assetid: 5affca77-1999-4507-a2b2-9aa226611b4b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 742ea2fedff2e4f044e46242a4152c12855ab15e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396156"
---
# <a name="destroying-frame-windows"></a>フレーム ウィンドウの破棄

MFC フレームワークは、フレームワークのドキュメントとビューに関連付けられているこれらのウィンドウの作成とウィンドウの破棄を管理します。 追加のウィンドウを作成する場合は、それらを破棄する必要があります。

ユーザーがウィンドウの既定値であるフレーム ウィンドウを閉じるときに、フレームワークで[OnClose](../mfc/reference/cwnd-class.md#onclose)ハンドラー呼び出し[DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow)します。 Windows のウィンドウが破棄されるときに呼び出されます最後のメンバー関数は[OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy)、呼び出しを行ういくつかのクリーンアップ、[既定](../mfc/reference/cwnd-class.md#default)メンバーが Windows のクリーンアップを実行する関数を呼び出す最後に、仮想メンバー関数[PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy)します。 [CFrameWnd](../mfc/reference/cframewnd-class.md)の実装`PostNcDestroy`C++ ウィンドウ オブジェクトを削除します。 C++ を使用しないでください**削除**フレーム ウィンドウの演算子。 代わりに、`DestroyWindow` を使用してください。

メイン ウィンドウが閉じるときに、アプリケーションを閉じます。 未保存のドキュメントを変更は、フレームワークは、ドキュメントを保存するかどうかを確認するメッセージ ボックスが表示され、確実に必要な場合、適切なドキュメントを保存します。

## <a name="what-do-you-want-to-know-more-about"></a>方法については、するして操作を行います

- [ドキュメント フレーム ウィンドウの作成](../mfc/creating-document-frame-windows.md)

## <a name="see-also"></a>関連項目

[フレーム ウィンドウの使用](../mfc/using-frame-windows.md)

