---
title: クラスをサポートします。
ms.date: 06/13/2019
f1_keywords:
- ISupportErrorInfoImpl
- ATLCOM/ATL::ISupportErrorInfoImpl
- ATLCOM/ATL::ISupportErrorInfoImpl::InterfaceSupportsErrorInfo
helpviewer_keywords:
- ISupportErrorInfo ATL implementation
- ISupportErrorInfoImpl class
- error information, ATL
ms.assetid: e33a4b11-a123-41cf-bcea-7b19743902af
ms.openlocfilehash: 4c60b58ba697f00b146077a2cdecd727fe2cac02
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326363"
---
# <a name="isupporterrorinfoimpl-class"></a>クラスをサポートします。

このクラスは[、ISupportErrorInfo インターフェイス](/windows/win32/api/oaidl/nn-oaidl-isupporterrorinfo)の既定の実装を提供し、1 つのインターフェイスのみがオブジェクトにエラーを生成するときに使用できます。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```cpp
template<const IID* piid>
class ATL_NO_VTABLE ISupportErrorInfoImpl
   : public ISupportErrorInfo
```

### <a name="parameters"></a>パラメーター

*ピッド*<br/>
[IErrorInfo](/windows/win32/api/oaidl/nn-oaidl-ierrorinfo)をサポートするインターフェイスの IID へのポインター。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[インターフェイスサポートエラー情報](#interfacesupportserrorinfo)|によって`riid`識別されるインターフェイスが[IErrorInfo](/windows/win32/api/oaidl/nn-oaidl-ierrorinfo)インターフェイスをサポートするかどうかを示します。|

## <a name="remarks"></a>解説

[ISupportErrorInfo インターフェイス](/windows/win32/api/oaidl/nn-oaidl-isupporterrorinfo)は、エラー情報をクライアントに返すことを保証します。 を使用`IErrorInfo`するオブジェクトは`ISupportErrorInfo`、 を実装する必要があります。

Class`ISupportErrorInfoImpl`は、オブジェクトに`ISupportErrorInfo`対して 1 つのインターフェイスだけがエラーを生成する場合に、デフォルトの実装を提供し、使用できます。 次に例を示します。

[!code-cpp[NVC_ATL_COM#48](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_1.h)]

## <a name="inheritance-hierarchy"></a>継承階層

`ISupportErrorInfo`

`ISupportErrorInfoImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="isupporterrorinfoimplinterfacesupportserrorinfo"></a><a name="interfacesupportserrorinfo"></a>インターフェイスサポートエラー情報

によって`riid`識別されるインターフェイスが[IErrorInfo](/windows/win32/api/oaidl/nn-oaidl-ierrorinfo)インターフェイスをサポートするかどうかを示します。

```cpp
STDMETHOD(InterfaceSupportsErrorInfo)(REFIID riid);
```

### <a name="remarks"></a>解説

次を参照[してください](/windows/win32/api/oaidl/nf-oaidl-isupporterrorinfo-interfacesupportserrorinfo)。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
