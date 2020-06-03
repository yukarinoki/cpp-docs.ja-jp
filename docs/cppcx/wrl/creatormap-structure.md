---
title: CreatorMap 構造体
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreatorMap
- implements/Microsoft::WRL::Details::CreatorMap
- module/Microsoft::WRL::Details::CreatorMap::activationId
- module/Microsoft::WRL::Details::CreatorMap::factoryCache
- module/Microsoft::WRL::Details::CreatorMap::factoryCreator
- module/Microsoft::WRL::Details::CreatorMap::serverName
helpviewer_keywords:
- Microsoft::WRL::Details::CreatorMap structure
- Microsoft::WRL::Details::CreatorMap::activationId data member
- Microsoft::WRL::Details::CreatorMap::factoryCache data member
- Microsoft::WRL::Details::CreatorMap::factoryCreator data member
- Microsoft::WRL::Details::CreatorMap::serverName data member
ms.assetid: 94e40927-90c3-4107-bca3-3ad2dc4beda9
ms.openlocfilehash: 1527f81694d1d809d585f3f6504c0e6433a2c26b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372602"
---
# <a name="creatormap-structure"></a>CreatorMap 構造体

Windows ランタイム C++ テンプレート ライブラリ インフラストラクチャをサポートし、コードから直接使用することを意図していません。

## <a name="syntax"></a>構文

```cpp
struct CreatorMap;
```

## <a name="remarks"></a>解説

オブジェクトの初期化、登録、および登録解除の方法について説明します。

`CreatorMap`には次の情報が含まれます。

- オブジェクトを初期化、登録、および登録解除する方法。

- 従来の COM または Windows ランタイム ファクトリに応じてアクティブ化データを比較する方法。

- インターフェイスのファクトリ キャッシュとサーバー名に関する情報。

## <a name="members"></a>メンバー

### <a name="public-data-members"></a>パブリック データ メンバー

名前                                          | 説明
--------------------------------------------- | ------------------------------------------------------------------------------------------------------
[作成者マップ::アクティベーションId](#activationid)     | 従来の COM クラス ID または Windows ランタイム名によって識別されるオブジェクト ID を表します。
[クリエイターマップ::ファクトリーキャッシュ](#factorycache)     | のファクトリ キャッシュへのポインターを格納します`CreatorMap`。
[クリエイターマップ::ファクトリークリエーター](#factorycreator) | 指定したのファクトリを作成`CreatorMap`します。
[作成者マップ::サーバー名](#servername)         | のサーバー名を格納します`CreatorMap`。

## <a name="inheritance-hierarchy"></a>継承階層

`CreatorMap`

## <a name="requirements"></a>必要条件

**ヘッダー:** モジュール.h

**名前空間:** マイクロソフト::WRL::Dのテール

## <a name="creatormapactivationid"></a><a name="activationid"></a>作成者マップ::アクティベーションId

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
union {
   const IID* clsid;
   const wchar_t* (*getRuntimeName)();
} activationId;
```

### <a name="parameters"></a>パラメーター

*Clsid*<br/>
インターフェイス ID。

*ランタイム名を取得します。*<br/>
オブジェクトの Windows ランタイム名を取得する関数。

### <a name="remarks"></a>解説

クラシック COM クラス ID または Windows ランタイム名によって識別されるオブジェクト ID を表します。

## <a name="creatormapfactorycache"></a><a name="factorycache"></a>クリエイターマップ::ファクトリーキャッシュ

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
FactoryCache* factoryCache;
```

### <a name="remarks"></a>解説

のファクトリ キャッシュへのポインターを格納します`CreatorMap`。

## <a name="creatormapfactorycreator"></a><a name="factorycreator"></a>クリエイターマップ::ファクトリークリエーター

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
HRESULT (*factoryCreator)(
   unsigned int* currentflags,
   const CreatorMap* entry,
   REFIID iidClassFactory,
IUnknown** factory);
```

### <a name="parameters"></a>パラメーター

*現在のフラグ*<br/>
列挙子の 1[つ](runtimeclasstype-enumeration.md)。

*エントリ*<br/>
クリエイターマップ。

*アイドクラスファクトリー*<br/>
クラス ファクトリのインターフェイス ID。

*factory*<br/>
操作が完了すると、クラス ファクトリのアドレス。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

### <a name="remarks"></a>解説

指定した CreatorMap のファクトリを作成します。

## <a name="creatormapservername"></a><a name="servername"></a>作成者マップ::サーバー名

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
const wchar_t* serverName;
```

### <a name="remarks"></a>解説

作成者マップのサーバー名を格納します。
