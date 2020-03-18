---
title: ドキュメント テンプレート クラス
ms.date: 11/04/2016
helpviewer_keywords:
- document templates [MFC], classes
ms.assetid: 901749e9-8048-44a0-b5e2-361554650a73
ms.openlocfilehash: 82b9ce4c242df7c85ada0722b2c1e993a0cf3f81
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446916"
---
# <a name="document-template-classes"></a>ドキュメント テンプレート クラス

ドキュメントテンプレートオブジェクトは、新しいドキュメントまたはビューが作成されたときに、ドキュメント、ビュー、およびフレームウィンドウオブジェクトの作成を調整します。

[CDocTemplate](../mfc/reference/cdoctemplate-class.md)<br/>
ドキュメントテンプレートの基本クラスです。 このクラスを直接使用することはありません。代わりに、このクラスから派生した他のドキュメントテンプレートクラスの1つを使用します。

[CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md)<br/>
マルチドキュメントインターフェイス (MDI) のドキュメント用のテンプレート。 MDI アプリケーションでは、一度に複数のドキュメントを開くことができます。

[CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md)<br/>
シングルドキュメントインターフェイス (SDI) のドキュメント用のテンプレート。 SDI アプリケーションは、一度に1つのドキュメントを開いているだけです。

## <a name="related-class"></a>関連クラス

[CCreateContext](../mfc/reference/ccreatecontext-structure.md)<br/>
ドキュメント、ビュー、およびフレームウィンドウオブジェクトの作成を調整するために、ドキュメントテンプレートによってウィンドウ作成関数に渡される構造体。

## <a name="see-also"></a>参照

[クラスの概要](../mfc/class-library-overview.md)
