---
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
ms.openlocfilehash: 507d35179b9fa86399e56b18171800f41eaf1f10
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371482"
---
# <a name="factorycache-structure"></a>FactoryCache 構造体

Windows ランタイム C++ テンプレート ライブラリ インフラストラクチャをサポートし、コードから直接使用することを意図していません。

## <a name="syntax"></a>構文

```cpp
struct FactoryCache;
```

## <a name="remarks"></a>解説

クラス ファクトリの場所と、登録された wrt オブジェクトまたは COM クラス オブジェクトを識別する値を格納します。

## <a name="members"></a>メンバー

### <a name="public-data-members"></a>パブリック データ メンバー

名前                              | 説明
--------------------------------- | ------------------------------------------------------------------------------------------------------------------------------
[クッキー](#cookie)   | 登録済みの Windows ランタイムまたは COM クラス オブジェクトを識別する値を格納し、後でオブジェクトの登録を解除するために使用します。
[ファクトリーキャッシュ::ファクトリー](#factory) | Windows ランタイムまたは COM クラス ファクトリへのポイント。

## <a name="inheritance-hierarchy"></a>継承階層

`FactoryCache`

## <a name="requirements"></a>必要条件

**ヘッダー:** モジュール.h

**名前空間:** マイクロソフト::WRL::Dのテール

## <a name="factorycachecookie"></a><a name="cookie"></a>クッキー

Windows ランタイム C++ テンプレート ライブラリ インフラストラクチャをサポートし、コードから直接使用することを意図していません。

```cpp
union {
   WINRT_REGISTRATION_COOKIE winrt;
   DWORD com;
} cookie;
```

### <a name="remarks"></a>解説

登録済みの Windows ランタイムまたは COM クラス オブジェクトを識別する値を格納し、後でオブジェクトの登録を解除するために使用します。

## <a name="factorycachefactory"></a><a name="factory"></a>ファクトリーキャッシュ::ファクトリー

Windows ランタイム C++ テンプレート ライブラリ インフラストラクチャをサポートし、コードから直接使用することを意図していません。

```cpp
IUnknown* factory;
```

### <a name="remarks"></a>解説

Windows ランタイムまたは COM クラス ファクトリへのポイント。
