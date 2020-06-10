---
title: ドキュメント テンプレート クラス
ms.date: 11/04/2016
helpviewer_keywords:
- document templates [MFC], classes
ms.assetid: 901749e9-8048-44a0-b5e2-361554650a73
ms.openlocfilehash: dffde80093f98fc1c81a6c20dfaf92b82e3b4c78
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618981"
---
# <a name="document-template-classes"></a>ドキュメント テンプレート クラス

ドキュメントテンプレートオブジェクトは、新しいドキュメントまたはビューが作成されたときに、ドキュメント、ビュー、およびフレームウィンドウオブジェクトの作成を調整します。

[CDocTemplate](reference/cdoctemplate-class.md)<br/>
ドキュメントテンプレートの基本クラスです。 このクラスを直接使用することはありません。代わりに、このクラスから派生した他のドキュメントテンプレートクラスの1つを使用します。

[CMultiDocTemplate](reference/cmultidoctemplate-class.md)<br/>
マルチドキュメントインターフェイス (MDI) のドキュメント用のテンプレート。 MDI アプリケーションでは、一度に複数のドキュメントを開くことができます。

[CSingleDocTemplate](reference/csingledoctemplate-class.md)<br/>
シングルドキュメントインターフェイス (SDI) のドキュメント用のテンプレート。 SDI アプリケーションは、一度に1つのドキュメントを開いているだけです。

## <a name="related-class"></a>関連クラス

[CCreateContext](reference/ccreatecontext-structure.md)<br/>
ドキュメント、ビュー、およびフレームウィンドウオブジェクトの作成を調整するために、ドキュメントテンプレートによってウィンドウ作成関数に渡される構造体。

## <a name="see-also"></a>関連項目

[クラスの概要](class-library-overview.md)
