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
ms.openlocfilehash: 04cb93b8ce3699b579342d33c0dae77176878379
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625297"
---
# <a name="ole-automation-classes"></a>OLE オートメーション クラス

これらのクラスは、オートメーションクライアント (他のアプリケーションを制御するアプリケーション) をサポートしています。 オートメーションサーバー (他のアプリケーションで制御できるアプリケーション) は、[ディスパッチマップ](reference/dispatch-maps.md)を通じてサポートされます。

[COleDispatchDriver](reference/coledispatchdriver-class.md)<br/>
オートメーションクライアントからオートメーションサーバーを呼び出すために使用されます。 クラスを追加するときに、このクラスを使用して、タイプライブラリを提供するオートメーションサーバーのタイプセーフなクラスを作成します。

[COleDispatchException](reference/coledispatchexception-class.md)<br/>
OLE オートメーション中のエラーによって発生する例外。 オートメーションの例外はオートメーションサーバーによってスローされ、オートメーションクライアントによってキャッチされます。

## <a name="see-also"></a>関連項目

[クラスの概要](class-library-overview.md)
