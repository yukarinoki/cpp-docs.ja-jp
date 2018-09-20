---
title: 一般的なウィンドウ作成順序 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- sequence [MFC], window creation
- frame windows [MFC], creating
- windows [MFC], creating
- sequence [MFC]
ms.assetid: 9cd8c7ea-5e24-429e-b6d9-d7b6041d8ba6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9336e5fa19b373f07c54e758a6f939bbc63e50ec
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46432790"
---
# <a name="general-window-creation-sequence"></a>一般的なウィンドウ作成順序

フレームワークではるかのと同じプロセスを使用して、説明した子などの独自のウィンドウのウィンドウを作成するときに[ドキュメント/ビューの作成](../mfc/document-view-creation.md)です。

MFC の採用によって提供されるすべてのウィンドウ クラス[2 段階構築](../mfc/one-stage-and-two-stage-construction-of-objects.md)します。 つまり、C++ の呼び出し中に**新しい**演算子、コンス トラクターは、割り当てと C++ オブジェクトを初期化しますが、対応する Windows ウィンドウを作成できません。 後で呼び出すことによって実現されます、[作成](../mfc/reference/cwnd-class.md#create)ウィンドウ オブジェクトのメンバー関数。

`Create`メンバー関数は、Windows のウィンドウを格納してその`HWND`C++ オブジェクトのパブリック データ メンバーに[m_hWnd](../mfc/reference/cwnd-class.md#m_hwnd)します。 `Create` 完全な作成パラメーターの柔軟性。 呼び出しの前に`Create`、グローバル関数をウィンドウ クラスを登録する[AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass)フレームのアイコンとクラスのスタイルを設定するためにします。

フレーム ウィンドウを使用することができます、 [LoadFrame](../mfc/reference/cframewnd-class.md#loadframe)メンバー関数の代わりに`Create`します。 `LoadFrame` 少ないパラメーターを使用して Windows のウィンドウになります。 フレームのキャプション、アイコン、アクセラレータ テーブル、およびメニューなどのリソースから多くの既定値を取得します。

> [!NOTE]
>  アイコン、アクセラレータ テーブル、およびメニュー リソースが必要、共通のリソース ID など**IDR_MAINFRAME**、LoadFrame によって読み込まれることにします。

## <a name="what-do-you-want-to-know-more-about"></a>方法については、するして操作を行います

- [ウィンドウ オブジェクト](../mfc/window-objects.md)

- [ウィンドウ「クラス」の登録](../mfc/registering-window-classes.md)

- [ウィンドウ オブジェクトの破棄](../mfc/destroying-window-objects.md)

- [ドキュメント フレーム ウィンドウの作成](../mfc/creating-document-frame-windows.md)

## <a name="see-also"></a>関連項目

[ウィンドウの作成](../mfc/creating-windows.md)

