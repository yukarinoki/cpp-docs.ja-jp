---
description: 詳細については、「ツールヒントの有効化」を参照してください。
title: ツール ヒントを有効にする方法
ms.date: 11/04/2016
helpviewer_keywords:
- initializing tool tips [MFC]
- enabling tool tips [MFC]
- tool tips [MFC], initializing
- tool tips [MFC], enabling
ms.assetid: 06b7c889-7722-4ce6-8b88-9efa50fe6369
ms.openlocfilehash: 677d2cc071e87f62f9bd2e700d8fdba166dfdee7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290948"
---
# <a name="enabling-tool-tips"></a>ツール ヒントを有効にする方法

ウィンドウの子コントロール (フォームビューやダイアログボックスのコントロールなど) に対して、ツールヒントのサポートを有効にすることができます。

### <a name="to-enable-tool-tips-for-the-child-controls-of-a-window"></a>ウィンドウの子コントロールのツールヒントを有効にするには

1. `EnableToolTips`ツールヒントを提供するウィンドウに対してを呼び出します。

1. [TTN_NEEDTEXT 通知](handling-ttn-needtext-notification-for-tool-tips.md)ハンドラーの各コントロールに文字列を指定します。 ハンドラーは、子コントロール (たとえば、フォームビュークラス) を含むウィンドウのメッセージマップにあります。 このハンドラーは、コントロールを識別する関数を呼び出し、 **Psztext** を設定して、ツールヒントコントロールによって使用されるテキストを指定します。

## <a name="see-also"></a>関連項目

[CFrameWnd から派生していない Windows のツールヒント](tool-tips-in-windows-not-derived-from-cframewnd.md)
