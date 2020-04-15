---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CFirePropNotifyEvent
- ATLCTL/ATL::CFirePropNotifyEvent
- ATLCTL/ATL::CFirePropNotifyEvent::FireOnChanged
- ATLCTL/ATL::CFirePropNotifyEvent::FireOnRequestEdit
helpviewer_keywords:
- sinks, notifying of ATL events
- CFirePropNotifyEvent class
- connection points [C++], notifying of events
ms.assetid: eb7a563e-6bce-4cdf-8d20-8c6a5307781b
ms.openlocfilehash: 1dfce42176341d74ffc7d9b42f856e71b17bf4f5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326970"
---
# <a name="cfirepropnotifyevent-class"></a>クラス

このクラスには、コントロール プロパティの変更に関するコンテナーのシンクに通知するメソッドが用意されています。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CFirePropNotifyEvent
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[イベント::火災が変更されました](#fireonchanged)|(静的)コントロール プロパティが変更されたことをコンテナーのシンクに通知します。|
|[イベント:::イベントを送信します。](#fireonrequestedit)|(静的)コントロール プロパティが変更されようとしていることをコンテナーのシンクに通知します。|

## <a name="remarks"></a>解説

`CFirePropNotifyEvent`には、コントロール プロパティが変更されたか、変更されようとしていることをコンテナーのシンクに通知する 2 つのメソッドがあります。

コントロールを`IPropertyNotifySink`実装するクラスが から派生している場合`CFirePropNotifyEvent`、メソッドは 呼び出`FireOnRequestEdit`し`FireOnChanged`時に呼び出されます。 コントロール クラスが から`IPropertyNotifySink`派生していない場合、これらの関数の呼び出しはS_OK返します。

コントロールの作成の詳細については[、「ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlctl.h

## <a name="cfirepropnotifyeventfireonchanged"></a><a name="fireonchanged"></a>イベント::火災が変更されました

接続されているすべての[IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink)インターフェイス (オブジェクトのすべてのコネクション ポイント) に、指定したオブジェクト プロパティが変更されたことを通知します。

```
static HRESULT FireOnChanged(IUnknown* pUnk, DISPID dispID);
```

### <a name="parameters"></a>パラメーター

*パンク*<br/>
[in]通知を送信`IUnknown`するオブジェクトへのポインター。

*Dispid*<br/>
[in]変更されたプロパティの識別子。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="remarks"></a>解説

この関数は、コントロールがコネクション ポイントをサポートしていない場合でも、安全に呼び出します。

## <a name="cfirepropnotifyeventfireonrequestedit"></a><a name="fireonrequestedit"></a>イベント:::イベントを送信します。

接続されているすべての[IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink)インターフェイス (オブジェクトのすべてのコネクション ポイント) に、指定したオブジェクト プロパティが変更されようとしていることを通知します。

```
static HRESULT FireOnRequestEdit(IUnknown* pUnk, DISPID dispID);
```

### <a name="parameters"></a>パラメーター

*パンク*<br/>
[in]通知を送信`IUnknown`するオブジェクトへのポインター。

*Dispid*<br/>
[in]変更しようとしているプロパティの識別子。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="remarks"></a>解説

この関数は、コントロールがコネクション ポイントをサポートしていない場合でも、安全に呼び出します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
