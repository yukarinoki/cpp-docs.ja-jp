---
title: ISupportErrorInfoImpl クラス
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
ms.openlocfilehash: 650d90c9ec98754e11586f63e0871b70ebbe34f3
ms.sourcegitcommit: e79188287189b76b34eb7e8fb1bfe646bdb586bc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2019
ms.locfileid: "67141703"
---
# <a name="isupporterrorinfoimpl-class"></a>ISupportErrorInfoImpl クラス

このクラスの既定の実装を提供する、 [ISupportErrorInfo インターフェイス](/windows/desktop/api/oaidl/nn-oaidl-isupporterrorinfo)1 つのインターフェイスのみがオブジェクトのエラーを生成するときに使用できます。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```cpp
template<const IID* piid>
class ATL_NO_VTABLE ISupportErrorInfoImpl
   : public ISupportErrorInfo
```

### <a name="parameters"></a>パラメーター

*piid*<br/>
サポートするインターフェイスの IID へのポインター [IErrorInfo](/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo)します。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ISupportErrorInfoImpl::InterfaceSupportsErrorInfo](#interfacesupportserrorinfo)|インターフェイスがで識別されるかどうかを示す`riid`サポート、 [IErrorInfo](/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo)インターフェイス。|

## <a name="remarks"></a>Remarks

[ISupportErrorInfo インターフェイス](/windows/desktop/api/oaidl/nn-oaidl-isupporterrorinfo)により、クライアントにエラー情報を返されることができます。 使用するオブジェクト`IErrorInfo`実装する必要があります`ISupportErrorInfo`します。

クラス`ISupportErrorInfoImpl`の既定の実装を提供します。 `ISupportErrorInfo` 、1 つのインターフェイスのみがオブジェクトのエラーを生成するときに使用できます。 例:

[!code-cpp[NVC_ATL_COM#48](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_1.h)]

## <a name="inheritance-hierarchy"></a>継承階層

`ISupportErrorInfo`

`ISupportErrorInfoImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

##  <a name="interfacesupportserrorinfo"></a>  ISupportErrorInfoImpl::InterfaceSupportsErrorInfo

インターフェイスがで識別されるかどうかを示す`riid`サポート、 [IErrorInfo](/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo)インターフェイス。

```cpp
STDMETHOD(InterfaceSupportsErrorInfo)(REFIID riid);
```

### <a name="remarks"></a>Remarks

参照してください[ISupportErrorInfo::InterfaceSupportsErrorInfo](/windows/desktop/api/oaidl/nf-oaidl-isupporterrorinfo-interfacesupportserrorinfo) Windows SDK にします。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
