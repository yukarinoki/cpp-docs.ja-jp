---
title: OLE オートメーション クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.ole
dev_langs:
- C++
helpviewer_keywords:
- Automation, classes
- Automation classes [MFC], OLE classes
- OLE Automation [MFC], classes
- Automation classes [MFC]
- OLE Automation [MFC]
ms.assetid: 96e5372b-ff8a-4da1-933b-4d9bbf4dceb3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ea35e51296b2fc528657c4dd9f9b9b76b84aae83
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391515"
---
# <a name="ole-automation-classes"></a>OLE オートメーション クラス

これらのクラスは、オートメーション クライアント (他のアプリケーションを制御するアプリケーション) をサポートします。 オートメーション サーバー (他のアプリケーションで制御できるアプリケーション) を通じてサポートされます[ディスパッチ マップ](../mfc/reference/dispatch-maps.md)します。

[COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md)<br/>
オートメーション クライアントからのオートメーション サーバーの呼び出しに使用します。 クラスを追加するときにタイプ ライブラリを提供するオートメーション サーバー用のタイプ セーフなクラスを作成するこのクラスが使用されます。

[COleDispatchException](../mfc/reference/coledispatchexception-class.md)<br/>
OLE オートメーションの中にエラーによる例外。 Automation の例外はオートメーション サーバーによってスローされ、オートメーション クライアントによってキャッチします。

## <a name="see-also"></a>関連項目

[クラスの概要](../mfc/class-library-overview.md)

