---
title: FactoryCache 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 09/21/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::FactoryCache
- module/Microsoft::WRL::Details::FactoryCache::cookie
- module/Microsoft::WRL::Details::FactoryCache::factory
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::FactoryCache structure
- Microsoft::WRL::Details::FactoryCache::cookie data member
- Microsoft::WRL::Details::FactoryCache::factory data member
ms.assetid: 624544e6-0989-47f6-a3e9-edb60e1ee6d4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d56779b5df33f75c9147d34b55f8c2fc65204a82
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2018
ms.locfileid: "48234542"
---
# <a name="factorycache-structure"></a>FactoryCache 構造体

Windows ランタイム C++ テンプレート ライブラリのインフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
struct FactoryCache;
```

## <a name="remarks"></a>Remarks

クラス ファクトリと、登録されている wrt を識別する値または COM クラスのオブジェクトの場所が含まれています。

## <a name="members"></a>メンバー

### <a name="public-data-members"></a>パブリック データ メンバー

名前                              | 説明
--------------------------------- | ------------------------------------------------------------------------------------------------------------------------------
[Factorycache::cookie](#cookie)   | 登録済み Windows ランタイムまたは COM クラスのオブジェクトを識別し、オブジェクトの登録を解除する際に使用する値が含まれています。
[Factorycache::factory](#factory) | Windows ランタイムまたは COM クラス ファクトリを指します。

## <a name="inheritance-hierarchy"></a>継承階層

`FactoryCache`

## <a name="requirements"></a>要件

**ヘッダー:** module.h

**Namespace:** Microsoft::WRL::Details

## <a name="cookie"></a>Factorycache::cookie

Windows ランタイム C++ テンプレート ライブラリのインフラストラクチャをサポートし、コードから直接使用するものではありません。

```cpp
union {
   WINRT_REGISTRATION_COOKIE winrt;
   DWORD com;
} cookie;
```

### <a name="remarks"></a>Remarks

登録済み Windows ランタイムまたは COM クラスのオブジェクトを識別し、オブジェクトの登録を解除する際に使用する値が含まれています。

## <a name="factory"></a>Factorycache::factory

Windows ランタイム C++ テンプレート ライブラリのインフラストラクチャをサポートし、コードから直接使用するものではありません。

```cpp
IUnknown* factory;
```

### <a name="remarks"></a>Remarks

Windows ランタイムまたは COM クラス ファクトリを指します。
