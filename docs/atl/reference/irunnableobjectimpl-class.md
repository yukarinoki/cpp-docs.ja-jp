---
title: クラスを実行可能なオブジェクトの一次
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
ms.openlocfilehash: 2843c0c25a5c104ffbdff72255ac5d85cf53b1ee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329447"
---
# <a name="irunnableobjectimpl-class"></a>クラスを実行可能なオブジェクトの一次

このクラスは`IUnknown`[、IRunnable オブジェクト](/windows/win32/api/objidl/nn-objidl-irunnableobject)インターフェイスの既定の実装を実装し、提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class T>
class IRunnableObjectImpl
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス`IRunnableObjectImpl`。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[実行可能なオブジェクトのImpl::Getランニングクラス](#getrunningclass)|実行中のコントロールの CLSID を返します。 ATL 実装では、CLSID をGUID_NULLに設定し、E_UNEXPECTED返します。|
|[実行可能なオブジェクトのImpl::実行中](#isrunning)|コントロールが実行されているかどうかを判断します。 ATL の実装は TRUE を返します。|
|[実行可能なオブジェクトのImpl::ロックランニング](#lockrunning)|コントロールを実行状態にロックします。 ATL 実装はS_OKを返します。|
|[実行可能なオブジェクトのImpl::実行](#run)|コントロールを強制的に実行します。 ATL 実装はS_OKを返します。|
|[オブジェクトの作成を実行できます。](#setcontainedobject)|コントロールが埋め込まれていることを示します。 ATL 実装はS_OKを返します。|

## <a name="remarks"></a>解説

[IRunnableObject](/windows/win32/api/objidl/nn-objidl-irunnableobject)インターフェイスを使用すると、コンテナーは、コントロールが実行されているかどうかを確認し、強制的に実行するか、またはコントロールを実行状態にロックできます。 Class`IRunnableObjectImpl`は、このインターフェイスの既定の実装を`IUnknown`提供し、デバッグ ビルドでダンプ デバイスに情報を送信することによって実装します。

**関連記事** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md), [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IRunnableObject`

`IRunnableObjectImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlctl.h

## <a name="irunnableobjectimplgetrunningclass"></a><a name="getrunningclass"></a>実行可能なオブジェクトのImpl::Getランニングクラス

実行中のコントロールの CLSID を返します。

```
HRESULT GetRunningClass(LPCLSID lpClsid);
```

### <a name="return-value"></a>戻り値

ATL 実装は\**、lpClsid*を GUID_NULL に設定し、E_UNEXPECTED返します。

### <a name="remarks"></a>解説

Windows SDK[の「IRunnable オブジェクト::GetRunningクラス](/windows/win32/api/objidl/nf-objidl-irunnableobject-getrunningclass)」を参照してください。

## <a name="irunnableobjectimplisrunning"></a><a name="isrunning"></a>実行可能なオブジェクトのImpl::実行中

コントロールが実行されているかどうかを判断します。

```
virtual BOOL IsRunning();
```

### <a name="return-value"></a>戻り値

ATL の実装は TRUE を返します。

### <a name="remarks"></a>解説

「Windows SDK[で実行可能なオブジェクト::IsRunning」](/windows/win32/api/objidl/nf-objidl-irunnableobject-isrunning)を参照してください。

## <a name="irunnableobjectimpllockrunning"></a><a name="lockrunning"></a>実行可能なオブジェクトのImpl::ロックランニング

コントロールを実行状態にロックします。

```
HRESULT LockRunning(BOOL fLock, BOOL fLastUnlockCloses);
```

### <a name="return-value"></a>戻り値

ATL 実装はS_OKを返します。

### <a name="remarks"></a>解説

「Windows SDK[で実行できるオブジェクト::ロック実行](/windows/win32/api/objidl/nf-objidl-irunnableobject-lockrunning)」を参照してください。

## <a name="irunnableobjectimplrun"></a><a name="run"></a>実行可能なオブジェクトのImpl::実行

コントロールを強制的に実行します。

```
HRESULT Run(LPBINDCTX lpbc);
```

### <a name="return-value"></a>戻り値

ATL 実装はS_OKを返します。

### <a name="remarks"></a>解説

「Windows SDK[での実行」](/windows/win32/api/objidl/nf-objidl-irunnableobject-run)を参照してください。

## <a name="irunnableobjectimplsetcontainedobject"></a><a name="setcontainedobject"></a>オブジェクトの作成を実行できます。

コントロールが埋め込まれていることを示します。

```
HRESULT SetContainedObject(BOOL fContained);
```

### <a name="return-value"></a>戻り値

ATL 実装はS_OKを返します。

### <a name="remarks"></a>解説

Windows SDK[の「IRunnable オブジェクト::セット包含オブジェクト](/windows/win32/api/objidl/nf-objidl-irunnableobject-setcontainedobject)」を参照してください。

## <a name="see-also"></a>関連項目

[CCom コントロール クラス](../../atl/reference/ccomcontrol-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
