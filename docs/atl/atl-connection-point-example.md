---
title: ATL 接続ポイントの例
ms.date: 11/04/2016
helpviewer_keywords:
- connection points [C++], examples
- examples [ATL]
ms.assetid: a49721b7-f308-43de-8868-f662a94bc81a
ms.openlocfilehash: 3113637a3f777a56bc0b0994203ce709fbc189d5
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57265068"
---
# <a name="atl-connection-point-example"></a>ATL 接続ポイントの例

この例は、サポートするオブジェクトを示しています。 [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink)アウトゴーイング インターフェイスとして。

[!code-cpp[NVC_ATL_Windowing#84](../atl/codesnippet/cpp/atl-connection-point-example_1.h)]

指定するときに`IPropertyNotifySink`クラスを使用する送信インターフェイスとして[IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md)の代わりに`IConnectionPointImpl`します。 例:

[!code-cpp[NVC_ATL_Windowing#85](../atl/codesnippet/cpp/atl-connection-point-example_2.h)]

## <a name="see-also"></a>関連項目

[接続ポイント](../atl/atl-connection-points.md)
