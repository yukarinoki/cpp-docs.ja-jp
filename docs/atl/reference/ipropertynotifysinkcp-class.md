---
title: クラスを通知します。
ms.date: 11/04/2016
f1_keywords:
- IPropertyNotifySinkCP
- atlctl/ATL::IPropertyNotifySinkCP
helpviewer_keywords:
- connection points [C++], managing
- sinks, notifying of changes
- IPropertyNotifySinkCP class
ms.assetid: 1b41445e-bc88-4fa6-bb62-d68aacec2bd5
ms.openlocfilehash: c6d98bf5a6dfe5566839eb22bcd2bab2a9c28e4d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329611"
---
# <a name="ipropertynotifysinkcp-class"></a>クラスを通知します。

このクラスは、接続可能なオブジェクトの出力インターフェイスとして[IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink)インターフェイスを公開します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class T, class CDV = CComDynamicUnkArray>
class IPropertyNotifySinkCP
   : public IConnectionPointImpl<T, &IID_IPropertyNotifySink, CDV>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス`IPropertyNotifySinkCP`。

*CDV*<br/>
コネクション ポイントとそのシンク間の接続を管理するクラス。 デフォルト値は、無制限の接続を許可する[CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)です。 また、固定数の接続を指定する[CComUnkArray](../../atl/reference/ccomunkarray-class.md)を使用することもできます。

## <a name="remarks"></a>解説

`IPropertyNotifySinkCP`基本クラスを通じてすべてのメソッドを継承[します](../../atl/reference/iconnectionpointimpl-class.md)。

インターフェイス[を](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink)使用すると、シンク オブジェクトがプロパティの変更に関する通知を受け取ることができます。 クラス`IPropertyNotifySinkCP`は、接続可能なオブジェクトの発信インターフェイスとしてこのインターフェイスを公開します。 クライアントは、シンク上`IPropertyNotifySink`でメソッドを実装する必要があります。

インターフェイスを表す`IPropertyNotifySinkCP`コネクション ポイントを作成する場合からクラスを派生`IPropertyNotifySink`させます。

ATL でのコネクション ポイントの使用の詳細については、[記事「接続ポイント](../../atl/atl-connection-points.md)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlctl.h

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/iconnectionpointimpl-class.md)<br/>
[クラスをコンテナーします。](../../atl/reference/iconnectionpointcontainerimpl-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
