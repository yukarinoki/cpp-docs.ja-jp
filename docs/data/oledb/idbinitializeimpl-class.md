---
title: IDBInitializeImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IDBInitializeImpl<T>
- ATL::IDBInitializeImpl<T>
- IDBInitializeImpl
- ATL::IDBInitializeImpl
- ATL.IDBInitializeImpl
- IDBInitializeImpl.IDBInitializeImpl
- IDBInitializeImpl
- IDBInitializeImpl::IDBInitializeImpl
- Initialize
- IDBInitializeImpl::Initialize
- IDBInitializeImpl.Initialize
- IDBInitializeImpl.Uninitialize
- Uninitialize
- IDBInitializeImpl::Uninitialize
- ATL::IDBInitializeImpl::m_dwStatus
- IDBInitializeImpl.m_dwStatus
- ATL.IDBInitializeImpl.m_dwStatus
- IDBInitializeImpl::m_dwStatus
- IDBInitializeImpl<T>::m_dwStatus
- ATL.IDBInitializeImpl<T>.m_dwStatus
- ATL::IDBInitializeImpl<T>::m_dwStatus
- m_dwStatus
- ATL::IDBInitializeImpl<T>::m_pCUtlPropInfo
- m_pCUtlPropInfo
- IDBInitializeImpl::m_pCUtlPropInfo
- ATL.IDBInitializeImpl.m_pCUtlPropInfo
- IDBInitializeImpl<T>::m_pCUtlPropInfo
- IDBInitializeImpl.m_pCUtlPropInfo
- ATL::IDBInitializeImpl::m_pCUtlPropInfo
dev_langs:
- C++
helpviewer_keywords:
- IDBInitializeImpl class
- IDBInitializeImpl constructor
- Initialize method
- Uninitialize method
- m_dwStatus
- m_pCUtlPropInfo
ms.assetid: e4182f81-0443-44f5-a0d3-e7e075d6f883
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 92d71bc780e66d4a61d74605aeb5c316b181beba
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50081765"
---
# <a name="idbinitializeimpl-class"></a>IDBInitializeImpl クラス

実装を提供、 [IDBInitialize](/previous-versions/windows/desktop/ms713706)インターフェイス。

## <a name="syntax"></a>構文

```cpp
template <class T>
class ATL_NO_VTABLE IDBInitializeImpl : public IDBInitialize
```

### <a name="parameters"></a>パラメーター

*T*<br/>
派生したクラス、`IDBInitializeImpl`します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[IDBInitializeImpl](#idbinitializeimpl)|コンストラクターです。|

### <a name="interface-methods"></a>インターフェイス メソッド

|||
|-|-|
|[Initialize](#initialize)|プロバイダーが開始されます。|
|[初期化を解除します。](#uninitialize)|プロバイダーを停止します。|

### <a name="data-members"></a>データ メンバー

|||
|-|-|
|[m_dwStatus](#dwstatus)|データ ソースのフラグ。|
|[m_pCUtlPropInfo](#pcutlpropinfo)|DB のプロパティ情報の実装へのポインター。|

## <a name="remarks"></a>Remarks

データ ソース オブジェクトと列挙子の省略可能なインターフェイスの必須のインターフェイスです。

## <a name="idbinitializeimpl"></a> Idbinitializeimpl::idbinitializeimpl

コンストラクターです。

### <a name="syntax"></a>構文

```cpp
IDBInitializeImpl();
```

### <a name="remarks"></a>Remarks

すべてのデータ メンバーを初期化します。

## <a name="initialize"></a> Idbinitializeimpl::initialize

そのプロパティのサポートを準備して、データ ソース オブジェクトを初期化します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(Initialize)(void);
```

### <a name="remarks"></a>Remarks

参照してください[idbinitialize::initialize](/previous-versions/windows/desktop/ms718026)で、 *OLE DB プログラマーズ リファレンス*します。

## <a name="uninitialize"></a> Idbinitializeimpl::uninitialize

データの場所はソース プロパティのサポートなどの内部リソースを解放して初期化されていない状態でのオブジェクトです。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(Uninitialize)(void);
```

### <a name="remarks"></a>Remarks

参照してください[:uninitialize](/previous-versions/windows/desktop/ms719648)で、 *OLE DB プログラマーズ リファレンス*します。

## <a name="dwstatus"></a> Idbinitializeimpl::m_dwstatus

データ ソースのフラグ。

### <a name="syntax"></a>構文

```cpp
DWORD m_dwStatus;
```

### <a name="remarks"></a>Remarks

これらのフラグは、データ ソース オブジェクトのさまざまな属性の状態を示すまたは指定します。 次の 1 つ以上含む**enum**値。

```cpp
enum DATASOURCE_FLAGS {
    DSF_MASK_INIT     = 0xFFFFF00F,
    DSF_PERSIST_DIRTY = 0x00000001,
    DSF_INITIALIZED   = 0x00000010,
};
```

|||
|-|-|
|`DSF_MASK_INIT`|初期化されていない状態の復元を有効にするマスク。|
|`DSF_PERSIST_DIRTY`|(変更されている) 場合は、データ ソース オブジェクトに永続化が必要な場合に設定します。|
|`DSF_INITIALIZED`|データ ソースが初期化されている場合に設定します。|

## <a name="pcutlpropinfo"></a> Idbinitializeimpl::m_pcutlpropinfo

DB のプロパティ情報の実装オブジェクトへのポインター。

### <a name="syntax"></a>構文

```cpp
CUtlPropInfo< T >* m_pCUtlPropInfo;
```

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)