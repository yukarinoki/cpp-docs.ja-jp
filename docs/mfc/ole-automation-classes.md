---
title: OLE オートメーション クラス
ms.date: 11/04/2016
helpviewer_keywords:
- Automation, classes
- Automation classes [MFC], OLE classes
- OLE Automation [MFC], classes
- Automation classes [MFC]
- OLE Automation [MFC]
ms.assetid: 96e5372b-ff8a-4da1-933b-4d9bbf4dceb3
ms.openlocfilehash: 644a4930eb55636ba6e87b949ed610b725334661
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447684"
---
# <a name="ole-automation-classes"></a>OLE オートメーション クラス

これらのクラスは、オートメーションクライアント (他のアプリケーションを制御するアプリケーション) をサポートしています。 オートメーションサーバー (他のアプリケーションで制御できるアプリケーション) は、[ディスパッチマップ](../mfc/reference/dispatch-maps.md)を通じてサポートされます。

[COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md)<br/>
オートメーションクライアントからオートメーションサーバーを呼び出すために使用されます。 クラスを追加するときに、このクラスを使用して、タイプライブラリを提供するオートメーションサーバーのタイプセーフなクラスを作成します。

[COleDispatchException](../mfc/reference/coledispatchexception-class.md)<br/>
OLE オートメーション中のエラーによって発生する例外。 オートメーションの例外はオートメーションサーバーによってスローされ、オートメーションクライアントによってキャッチされます。

## <a name="see-also"></a>参照

[クラスの概要](../mfc/class-library-overview.md)
