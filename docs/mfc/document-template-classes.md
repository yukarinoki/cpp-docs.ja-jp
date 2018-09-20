---
title: ドキュメント テンプレート クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.document
dev_langs:
- C++
helpviewer_keywords:
- document templates [MFC], classes
ms.assetid: 901749e9-8048-44a0-b5e2-361554650a73
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 87984bf06d8ca178d2a21ac8ff475f828690668e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46406062"
---
# <a name="document-template-classes"></a>ドキュメント テンプレート クラス

ドキュメント テンプレート オブジェクトがドキュメント、ビュー、および、新しいドキュメントのフレーム ウィンドウ オブジェクトの作成を調整またはビューを作成します。

[CDocTemplate](../mfc/reference/cdoctemplate-class.md)<br/>
ドキュメント テンプレートの基本クラスです。 このクラスを直接; 使用はしないでください。代わりに、このクラスから派生したその他のドキュメント テンプレート クラスのいずれかを使用します。

[CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md)<br/>
マルチ ドキュメント インターフェイス (MDI) 内のドキュメントのテンプレート。 MDI アプリケーションには、複数のドキュメントを同時に開くことができます。

[CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md)<br/>
シングル ドキュメント インターフェイス (SDI) 内のドキュメントのテンプレート。 SDI アプリケーションでは、同時に開く 1 つだけのドキュメントがあります。

## <a name="related-class"></a>関連クラス

[CCreateContext](../mfc/reference/ccreatecontext-structure.md)<br/>
構造体は、ドキュメント、ビュー、フレーム ウィンドウ オブジェクトの作成を調整するウィンドウの作成関数には、ドキュメント テンプレートで渡されます。

## <a name="see-also"></a>関連項目

[クラスの概要](../mfc/class-library-overview.md)

