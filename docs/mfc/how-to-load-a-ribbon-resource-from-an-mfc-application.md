---
title: '方法: MFC アプリケーションからリボン リソースを読み込む'
ms.date: 11/04/2016
helpviewer_keywords:
- ribbon resource [MFC], loading
ms.assetid: 1c76bb8f-6345-414a-9f3f-128815ceadc5
ms.openlocfilehash: 14ba37952d6f8849c51b36901a6bc17404f938e2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50515155"
---
# <a name="how-to-load-a-ribbon-resource-from-an-mfc-application"></a>方法: MFC アプリケーションからリボン リソースを読み込む

アプリケーションでリボン リソースを使用するには、リボン リソースを読み込むためのアプリケーションを変更します。

### <a name="to-load-a-ribbon-resource"></a>リボン リソースを読み込めません

1. 宣言、`Ribbon Control`オブジェクト、`CMainFrame`クラス。

```
    CMFCRibbonBar m_wndRibbonBar;
```

1. `CMainFrame::OnCreate`を作成し、リボン コントロールを初期化します。

```
    if (!m_wndRibbonBar.Create (this))
{
    return -1;
}

    if (!m_wndRibbonBar.LoadFromResource(IDR_RIBBON))
{
    return -1;
}
```

## <a name="see-also"></a>関連項目

[リボン デザイナー (MFC)](../mfc/ribbon-designer-mfc.md)

