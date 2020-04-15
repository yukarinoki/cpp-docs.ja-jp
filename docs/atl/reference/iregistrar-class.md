---
title: Iレジストラインターフェイス
ms.date: 02/01/2017
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
helpviewer_keywords:
- Iregistrar Interface
ms.assetid: e88c04b7-0c93-4ae8-aeb9-ecd78f87421e
ms.openlocfilehash: 98943fe294322715723bd91207a6f3320ca1ffb3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329461"
---
# <a name="iregistrar-interface"></a>Iレジストラインターフェイス

このインターフェイスは atliface.h で定義されており、CAtlModule メンバー関数 ([リソース D.](catlmodule-class.md#updateregistryfromresourced)

## <a name="syntax"></a>構文

```
typedef interface IRegistrar IRegistrar;
```

## <a name="remarks"></a>解説

詳細については、[置き換え可能パラメーターの使用 (レジストラーのプリプロセッサ) を](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)参照してください。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Iレジストラ::リソースレジスタSz](#resourceregistersz)|リソースを登録します。 |
|[Iレジストラ:::リソースアンレジスタSz](#resourceunregistersz)| リソースの登録を解除します。|
|[Iレジストラ::ファイルレジスタ](#fileregister)|ファイルを登録します。|
|[Iレジストラ::ファイル登録解除](#fileunregister)|ファイルの登録を解除します。|
|[Iレジストラ::文字列レジスタ](#stringregister)|文字列を登録します。|
|[Iレジストラ:::文字列登録解除](#stringunregister)|文字列の登録を解除します。|
|[Iレジストラ::リソースレジスタ](#resourceregister)|リソースを登録します。|
|[Iレジストラ::リソース登録解除](#resourceunregister)|リソースの登録を解除します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlifase.h

## <a name="iregistrarresourceregistersz"></a><a name="resourceregistersz"></a>Iレジストラ::リソースレジスタSz

リソースを登録します。

```
virtual HRESULT STDMETHODCALLTYPE ResourceRegisterSz(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_z_ LPCOLESTR szID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

## <a name="iregistrarresourceunregistersz"></a><a name="resourceunregistersz"></a>Iレジストラ:::リソースアンレジスタSz

リソースの登録を解除します。

```
virtual HRESULT STDMETHODCALLTYPE ResourceUnregisterSz(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_z_ LPCOLESTR szID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

## <a name="iregistrarfileregister"></a><a name="fileregister"></a>Iレジストラ::ファイルレジスタ

ファイルを登録します。

```
virtual HRESULT STDMETHODCALLTYPE FileRegister(
    /* [in] */ _In_z_ LPCOLESTR fileName) = 0;
```

## <a name="iregistrarfileunregister"></a><a name="fileunregister"></a>Iレジストラ::ファイル登録解除

ファイルの登録を解除します。

```
virtual HRESULT STDMETHODCALLTYPE FileUnregister(
    /* [in] */ _In_z_ LPCOLESTR fileName) = 0;
```

## <a name="iregistrarstringregister"></a><a name="stringregister"></a>Iレジストラ::文字列レジスタ

指定した文字列データを登録します。

```
virtual HRESULT STDMETHODCALLTYPE StringRegister(
    /* [in] */ _In_z_ LPCOLESTR data) = 0;
```

## <a name="iregistrarstringunregister"></a><a name="stringunregister"></a>Iレジストラ:::文字列登録解除

指定した文字列データの登録を解除します。

```
virtualHRESULT STDMETHODCALLTYPE StringUnregister(
    /* [in] */ _In_z_ LPCOLESTR data) = 0;
```

## <a name="iregistrarresourceregister"></a><a name="resourceregister"></a>Iレジストラ::リソースレジスタ

リソースを登録します。

```
virtual HRESULT STDMETHODCALLTYPE ResourceRegister(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_ UINT nID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

## <a name="iregistrarresourceunregister"></a><a name="resourceunregister"></a>Iレジストラ::リソース登録解除

リソースの登録を解除します。

```
virtualHRESULT STDMETHODCALLTYPE ResourceUnregister(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_ UINT nID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

## <a name="see-also"></a>関連項目

[置き換え可能パラメーターの使用 (レジストラのプリプロセッサ)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[モジュール クラス](../../atl/atl-module-classes.md)<br/>
[レジストリ コンポーネント (レジストラー)](../../atl/atl-registry-component-registrar.md)
