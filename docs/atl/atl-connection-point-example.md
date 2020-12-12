---
description: '詳細情報: ATL 接続ポイントの例'
title: ATL 接続ポイントの例
ms.date: 11/04/2016
helpviewer_keywords:
- connection points [C++], examples
- examples [ATL]
ms.assetid: a49721b7-f308-43de-8868-f662a94bc81a
ms.openlocfilehash: 6416720b5366838f9687f31947cac9a6824da058
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165811"
---
# <a name="atl-connection-point-example"></a>ATL 接続ポイントの例

次の例は、送信インターフェイスとして [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) をサポートするオブジェクトを示しています。

[!code-cpp[NVC_ATL_Windowing#84](../atl/codesnippet/cpp/atl-connection-point-example_1.h)]

を `IPropertyNotifySink` 送信インターフェイスとして指定する場合は、の代わりに [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) クラスを使用でき `IConnectionPointImpl` ます。 次に例を示します。

[!code-cpp[NVC_ATL_Windowing#85](../atl/codesnippet/cpp/atl-connection-point-example_2.h)]

## <a name="see-also"></a>関連項目

[接続ポイント](../atl/atl-connection-points.md)
