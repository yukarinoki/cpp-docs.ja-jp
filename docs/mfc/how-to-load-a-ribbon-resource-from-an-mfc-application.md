---
title: '方法: MFC アプリケーションからリボン リソースを読み込む |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ribbon resource [MFC], loading
ms.assetid: 1c76bb8f-6345-414a-9f3f-128815ceadc5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1643989a96a9003847fb53de624bff12cd51cd88
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46434294"
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

