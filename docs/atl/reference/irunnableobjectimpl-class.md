---
description: '詳細情報: IRunnableObjectImpl クラス'
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
ms.openlocfilehash: ecae31d23eb68ce45e9b140a3e5034fb6c5400fa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158115"
---
# <a name="irunnableobjectimpl-class"></a>IRunnableObjectImpl クラス

このクラス `IUnknown` はを実装し、 [IRunnableObject](/windows/win32/api/objidl/nn-objidl-irunnableobject) インターフェイスの既定の実装を提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class T>
class IRunnableObjectImpl
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス `IRunnableObjectImpl` 。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IRunnableObjectImpl::GetRunningClass](#getrunningclass)|実行中のコントロールの CLSID を返します。 ATL の実装では、CLSID が GUID_NULL に設定され、E_UNEXPECTED が返されます。|
|[IRunnableObjectImpl:: IsRunning](#isrunning)|コントロールが実行されているかどうかを判断します。 ATL の実装は TRUE を返します。|
|[IRunnableObjectImpl:: LockRunning](#lockrunning)|コントロールを実行中の状態にロックします。 ATL 実装は S_OK を返します。|
|[IRunnableObjectImpl:: Run](#run)|コントロールを強制的に実行します。 ATL 実装は S_OK を返します。|
|[IRunnableObjectImpl:: Set Edobject](#setcontainedobject)|コントロールが埋め込まれていることを示します。 ATL 実装は S_OK を返します。|

## <a name="remarks"></a>解説

[IRunnableObject](/windows/win32/api/objidl/nn-objidl-irunnableobject)インターフェイスを使用すると、コンテナーは、コントロールが実行されているかどうかを判断し、強制的に実行するか、実行中の状態にロックすることができます。 クラス `IRunnableObjectImpl` は、このインターフェイスの既定の実装を提供し、 `IUnknown` デバッグビルドでダンプデバイスに情報を送信することによってを実装します。

**関連記事** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [atl プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IRunnableObject`

`IRunnableObjectImpl`

## <a name="requirements"></a>要件

**ヘッダー:** atlctl. h

## <a name="irunnableobjectimplgetrunningclass"></a><a name="getrunningclass"></a> IRunnableObjectImpl::GetRunningClass

実行中のコントロールの CLSID を返します。

```
HRESULT GetRunningClass(LPCLSID lpClsid);
```

### <a name="return-value"></a>戻り値

ATL 実装は、 \* *lpclsid* を GUID_NULL に設定し、E_UNEXPECTED を返します。

### <a name="remarks"></a>解説

Windows SDK の「 [IRunnableObject:: GetRunningClass](/windows/win32/api/objidl/nf-objidl-irunnableobject-getrunningclass) 」を参照してください。

## <a name="irunnableobjectimplisrunning"></a><a name="isrunning"></a> IRunnableObjectImpl:: IsRunning

コントロールが実行されているかどうかを判断します。

```
virtual BOOL IsRunning();
```

### <a name="return-value"></a>戻り値

ATL の実装は TRUE を返します。

### <a name="remarks"></a>解説

Windows SDK の「 [IRunnableObject:: IsRunning](/windows/win32/api/objidl/nf-objidl-irunnableobject-isrunning) 」を参照してください。

## <a name="irunnableobjectimpllockrunning"></a><a name="lockrunning"></a> IRunnableObjectImpl:: LockRunning

コントロールを実行中の状態にロックします。

```
HRESULT LockRunning(BOOL fLock, BOOL fLastUnlockCloses);
```

### <a name="return-value"></a>戻り値

ATL 実装は S_OK を返します。

### <a name="remarks"></a>解説

Windows SDK の「 [IRunnableObject:: LockRunning](/windows/win32/api/objidl/nf-objidl-irunnableobject-lockrunning) 」を参照してください。

## <a name="irunnableobjectimplrun"></a><a name="run"></a> IRunnableObjectImpl:: Run

コントロールを強制的に実行します。

```
HRESULT Run(LPBINDCTX lpbc);
```

### <a name="return-value"></a>戻り値

ATL 実装は S_OK を返します。

### <a name="remarks"></a>解説

Windows SDK の「 [IRunnableObject:: Run](/windows/win32/api/objidl/nf-objidl-irunnableobject-run) 」を参照してください。

## <a name="irunnableobjectimplsetcontainedobject"></a><a name="setcontainedobject"></a> IRunnableObjectImpl:: Set Edobject

コントロールが埋め込まれていることを示します。

```
HRESULT SetContainedObject(BOOL fContained);
```

### <a name="return-value"></a>戻り値

ATL 実装は S_OK を返します。

### <a name="remarks"></a>解説

Windows SDK の「 [IRunnableObject:: Set Edobject](/windows/win32/api/objidl/nf-objidl-irunnableobject-setcontainedobject) 」を参照してください。

## <a name="see-also"></a>関連項目

[CComControl クラス](../../atl/reference/ccomcontrol-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
