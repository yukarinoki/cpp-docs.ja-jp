---
description: '詳細については、次を参照してください: FactoryCache 構造体'
title: FactoryCache 構造体
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::FactoryCache
- module/Microsoft::WRL::Details::FactoryCache::cookie
- module/Microsoft::WRL::Details::FactoryCache::factory
helpviewer_keywords:
- Microsoft::WRL::Details::FactoryCache structure
- Microsoft::WRL::Details::FactoryCache::cookie data member
- Microsoft::WRL::Details::FactoryCache::factory data member
ms.assetid: 624544e6-0989-47f6-a3e9-edb60e1ee6d4
ms.openlocfilehash: 3e9ee084a063eb8094c309dee412a8793801921b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198553"
---
# <a name="factorycache-structure"></a>FactoryCache 構造体

は、Windows ランタイム C++ テンプレートライブラリインフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
struct FactoryCache;
```

## <a name="remarks"></a>解説

クラスファクトリの場所と、登録されている wrt または COM クラスオブジェクトを識別する値を格納します。

## <a name="members"></a>メンバー

### <a name="public-data-members"></a>パブリック データ メンバー

名前                              | 説明
--------------------------------- | ------------------------------------------------------------------------------------------------------------------------------
[FactoryCache:: cookie](#cookie)   | 登録されている Windows ランタイムまたは COM クラスオブジェクトを識別する値を格納し、後でオブジェクトの登録を解除するために使用します。
[FactoryCache:: factory](#factory) | Windows ランタイムまたは COM クラスファクトリを指します。

## <a name="inheritance-hierarchy"></a>継承階層

`FactoryCache`

## <a name="requirements"></a>要件

**ヘッダー:** resource.h

**名前空間:** Microsoft:: WRL::D etails

## <a name="factorycachecookie"></a><a name="cookie"></a> FactoryCache:: cookie

は、Windows ランタイム C++ テンプレートライブラリインフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
union {
   WINRT_REGISTRATION_COOKIE winrt;
   DWORD com;
} cookie;
```

### <a name="remarks"></a>解説

登録されている Windows ランタイムまたは COM クラスオブジェクトを識別する値を格納し、後でオブジェクトの登録を解除するために使用します。

## <a name="factorycachefactory"></a><a name="factory"></a> FactoryCache:: factory

は、Windows ランタイム C++ テンプレートライブラリインフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
IUnknown* factory;
```

### <a name="remarks"></a>解説

Windows ランタイムまたは COM クラスファクトリを指します。
