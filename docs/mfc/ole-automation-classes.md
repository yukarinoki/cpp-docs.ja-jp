---
description: 詳細については、「OLE オートメーションクラス」を参照してください。
title: OLE オートメーション クラス
ms.date: 11/04/2016
helpviewer_keywords:
- Automation, classes
- Automation classes [MFC], OLE classes
- OLE Automation [MFC], classes
- Automation classes [MFC]
- OLE Automation [MFC]
ms.assetid: 96e5372b-ff8a-4da1-933b-4d9bbf4dceb3
ms.openlocfilehash: 588c684d17eb358183097cd4ed62432f334e3f0f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275569"
---
# <a name="ole-automation-classes"></a>OLE オートメーション クラス

これらのクラスは、オートメーションクライアント (他のアプリケーションを制御するアプリケーション) をサポートしています。 オートメーションサーバー (他のアプリケーションで制御できるアプリケーション) は、 [ディスパッチマップ](reference/dispatch-maps.md)を通じてサポートされます。

[COleDispatchDriver](reference/coledispatchdriver-class.md)<br/>
オートメーションクライアントからオートメーションサーバーを呼び出すために使用されます。 クラスを追加するときに、このクラスを使用して、タイプライブラリを提供するオートメーションサーバーのタイプセーフなクラスを作成します。

[COleDispatchException](reference/coledispatchexception-class.md)<br/>
OLE オートメーション中のエラーによって発生する例外。 オートメーションの例外はオートメーションサーバーによってスローされ、オートメーションクライアントによってキャッチされます。

## <a name="see-also"></a>関連項目

[クラスの概要](class-library-overview.md)
