---
title: IRegistrar インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 2/1/2017
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IRegistrar
- ATLIFASE/ATL::IRegistrar
- ATLIFASE/ATL::IRegistrar::ResourceRegisterSz
- ATLIFASE/ATL::IRegistrar::ResourceUnregisterSz
- ATLIFASE/ATL::IRegistrar::FileRegister
- ATLIFASE/ATL::IRegistrar::FileUnregister
- ATLIFASE/ATL::IRegistrar::StringRegister
- ATLIFASE/ATL::IRegistrar::StringUnregister
- ATLIFASE/ATL::IRegistrar::ResourceRegister
- ATLIFASE/ATL::IRegistrar::ResourceUnregister
dev_langs:
- C++
helpviewer_keywords:
- Iregistrar Interface
ms.assetid: e88c04b7-0c93-4ae8-aeb9-ecd78f87421e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9b445a0e1a2668047d34f18424f44b0dc7cc55f1
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43760920"
---
# <a name="iregistrar-interface"></a>IRegistrar インターフェイス

このインターフェイスは atliface.h で定義され、内部的に関数によって使用される CAtlModule メンバーなど[ため](catlmodule-class.md#updateregistryfromresourced)します。

## <a name="syntax"></a>構文

```
typedef interface IRegistrar IRegistrar;
```

## <a name="remarks"></a>Remarks

トピックを参照して[置き換え可能パラメーターの使用 (レジストラーのプリプロセッサ)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)の詳細。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IRegistrar::ResourceRegisterSz](#resourceregistersz)|リソースを登録します。 |
|[IRegistrar::ResourceUnregisterSz](#resourceunregistersz)| リソースを登録解除します。|
|[IRegistrar::FileRegister](#fileregister)|ファイルを登録します。|
|[IRegistrar::FileUnregister](#fileunregister)|ファイルを登録解除します。|
|[IRegistrar::StringRegister](#stringregister)|文字列を登録します。|
|[IRegistrar::StringUnregister](#stringunregister)|文字列の登録を解除します。|
|[IRegistrar::ResourceRegister](#resourceregister)|リソースを登録します。|
|[IRegistrar::ResourceUnregister](#resourceunregister)|リソースを登録解除します。|

## <a name="requirements"></a>要件

**ヘッダー:** atlifase.h

##  <a name="resourceregistersz"></a>  IRegistrar::ResourceRegisterSz

リソースを登録します。

```
virtual HRESULT STDMETHODCALLTYPE ResourceRegisterSz(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_z_ LPCOLESTR szID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

##  <a name="resourceunregistersz"></a>  IRegistrar::ResourceUnregisterSz

リソースを登録解除します。

```
virtual HRESULT STDMETHODCALLTYPE ResourceUnregisterSz(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_z_ LPCOLESTR szID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

##  <a name="fileregister"></a>  IRegistrar::FileRegister

ファイルを登録します。

```
virtual HRESULT STDMETHODCALLTYPE FileRegister(
    /* [in] */ _In_z_ LPCOLESTR fileName) = 0;
```

##  <a name="fileunregister"></a>  IRegistrar::FileUnregister

ファイルを登録解除します。

```
virtual HRESULT STDMETHODCALLTYPE FileUnregister(
    /* [in] */ _In_z_ LPCOLESTR fileName) = 0;
```

##  <a name="stringregister"></a>  IRegistrar::StringRegister

指定した文字列データを登録します。

```
virtual HRESULT STDMETHODCALLTYPE StringRegister(
    /* [in] */ _In_z_ LPCOLESTR data) = 0;
```

##  <a name="stringunregister"></a>  IRegistrar::StringUnregister

指定した文字列データを登録解除します。

```
virtualHRESULT STDMETHODCALLTYPE StringUnregister(
    /* [in] */ _In_z_ LPCOLESTR data) = 0;
```

##  <a name="resourceregister"></a>  IRegistrar::ResourceRegister

リソースを登録します。

```
virtual HRESULT STDMETHODCALLTYPE ResourceRegister(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_ UINT nID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

##  <a name="resourceunregister"></a>  IRegistrar::ResourceUnregister

リソースを登録解除します。

```
virtualHRESULT STDMETHODCALLTYPE ResourceUnregister(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_ UINT nID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

## <a name="see-also"></a>関連項目

[置き換え可能パラメーター (レジストラー プリプロセッサ) を使用します。](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)   
[クラスの概要](../../atl/atl-class-overview.md)   
[モジュール クラス](../../atl/atl-module-classes.md)   
[レジストリ コンポーネント (レジストラー)](../../atl/atl-registry-component-registrar.md)
