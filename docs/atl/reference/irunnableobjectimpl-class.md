---
title: IRunnableObjectImpl クラス
ms.date: 11/04/2016
f1_keywords:
- IRunnableObjectImpl
- ATLCTL/ATL::IRunnableObjectImpl
- ATLCTL/ATL::IRunnableObjectImpl::GetRunningClass
- ATLCTL/ATL::IRunnableObjectImpl::IsRunning
- ATLCTL/ATL::IRunnableObjectImpl::LockRunning
- ATLCTL/ATL::IRunnableObjectImpl::Run
- ATLCTL/ATL::IRunnableObjectImpl::SetContainedObject
helpviewer_keywords:
- containers, running controls
- IRunnableObjectImpl class
- IRunnableObject, ATL implementation
- controls [ATL], running
- controls [C++], container running in ATL
ms.assetid: 305c7c3b-889e-49dd-aca1-34379c1b9931
ms.openlocfilehash: 44b1e0ae1b72a40b45abe0650eb69a279b5a84d1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62200340"
---
# <a name="irunnableobjectimpl-class"></a>IRunnableObjectImpl クラス

このクラスは実装`IUnknown`の既定の実装を提供し、 [IRunnableObject](/windows/desktop/api/objidl/nn-objidl-irunnableobject)インターフェイス。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class T>
class IRunnableObjectImpl
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
派生したクラス、`IRunnableObjectImpl`します。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IRunnableObjectImpl::GetRunningClass](#getrunningclass)|実行中のコントロールの CLSID を返します。 ATL の実装では、CLSID を GUID_ に設定し、E_UNEXPECTED を返します。|
|[IRunnableObjectImpl::IsRunning](#isrunning)|コントロールが実行されているかどうかを決定します。 ATL の実装では、TRUE を返します。|
|[IRunnableObjectImpl::LockRunning](#lockrunning)|実行中の状態にコントロールをロックします。 ATL の実装では、S_OK を返します。|
|[IRunnableObjectImpl::Run](#run)|強制的にコントロールを実行します。 ATL の実装では、S_OK を返します。|
|[IRunnableObjectImpl::SetContainedObject](#setcontainedobject)|コントロールが埋め込まれていることを示します。 ATL の実装では、S_OK を返します。|

## <a name="remarks"></a>Remarks

[IRunnableObject](/windows/desktop/api/objidl/nn-objidl-irunnableobject)インターフェイスは、特定のコントロールが実行されているかどうか、実行、または実行中の状態にロックするように強制するためのコンテナーを使用できます。 クラス`IRunnableObjectImpl`このインターフェイスの既定の実装を提供し、実装`IUnknown`ダンプ情報を送信することによってデバッグでのデバイスをビルドします。

**関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IRunnableObject`

`IRunnableObjectImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlctl.h

##  <a name="getrunningclass"></a>  IRunnableObjectImpl::GetRunningClass

実行中のコントロールの CLSID を返します。

```
HRESULT GetRunningClass(LPCLSID lpClsid);
```

### <a name="return-value"></a>戻り値

ATL の実装設定\* *lpClsid* GUID_ を E_UNEXPECTED を返します。

### <a name="remarks"></a>Remarks

参照してください[IRunnableObject::GetRunningClass](/windows/desktop/api/objidl/nf-objidl-irunnableobject-getrunningclass) Windows SDK にします。

##  <a name="isrunning"></a>  IRunnableObjectImpl::IsRunning

コントロールが実行されているかどうかを決定します。

```
virtual BOOL IsRunning();
```

### <a name="return-value"></a>戻り値

ATL の実装では、TRUE を返します。

### <a name="remarks"></a>Remarks

参照してください[IRunnableObject::IsRunning](/windows/desktop/api/objidl/nf-objidl-irunnableobject-isrunning) Windows SDK にします。

##  <a name="lockrunning"></a>  IRunnableObjectImpl::LockRunning

実行中の状態にコントロールをロックします。

```
HRESULT LockRunning(BOOL fLock, BOOL fLastUnlockCloses);
```

### <a name="return-value"></a>戻り値

ATL の実装では、S_OK を返します。

### <a name="remarks"></a>Remarks

参照してください[IRunnableObject::LockRunning](/windows/desktop/api/objidl/nf-objidl-irunnableobject-lockrunning) Windows SDK にします。

##  <a name="run"></a>  IRunnableObjectImpl::Run

強制的にコントロールを実行します。

```
HRESULT Run(LPBINDCTX lpbc);
```

### <a name="return-value"></a>戻り値

ATL の実装では、S_OK を返します。

### <a name="remarks"></a>Remarks

参照してください[IRunnableObject::Run](/windows/desktop/api/objidl/nf-objidl-irunnableobject-run) Windows SDK にします。

##  <a name="setcontainedobject"></a>  IRunnableObjectImpl::SetContainedObject

コントロールが埋め込まれていることを示します。

```
HRESULT SetContainedObject(BOOL fContained);
```

### <a name="return-value"></a>戻り値

ATL の実装では、S_OK を返します。

### <a name="remarks"></a>Remarks

参照してください[IRunnableObject::SetContainedObject](/windows/desktop/api/objidl/nf-objidl-irunnableobject-setcontainedobject) Windows SDK にします。

## <a name="see-also"></a>関連項目

[CComControl クラス](../../atl/reference/ccomcontrol-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
