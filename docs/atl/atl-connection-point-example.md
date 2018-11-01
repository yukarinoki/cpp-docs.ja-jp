---
title: ATL 接続ポイントの例
ms.date: 11/04/2016
helpviewer_keywords:
- connection points [C++], examples
- examples [ATL]
ms.assetid: a49721b7-f308-43de-8868-f662a94bc81a
ms.openlocfilehash: 9312db740171672e6b0f231855408e0d0a9e060d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50495993"
---
# <a name="atl-connection-point-example"></a>ATL 接続ポイントの例

この例は、サポートするオブジェクトを示しています。 [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink)アウトゴーイング インターフェイスとして。

[!code-cpp[NVC_ATL_Windowing#84](../atl/codesnippet/cpp/atl-connection-point-example_1.h)]

指定するときに`IPropertyNotifySink`クラスを使用する送信インターフェイスとして[IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md)の代わりに`IConnectionPointImpl`します。 例えば:

[!code-cpp[NVC_ATL_Windowing#85](../atl/codesnippet/cpp/atl-connection-point-example_2.h)]

## <a name="see-also"></a>関連項目

[接続ポイント](../atl/atl-connection-points.md)

