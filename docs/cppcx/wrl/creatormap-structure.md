---
description: '詳細については、次を参照してください: CreatorMap 構造体'
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
ms.openlocfilehash: 0ef3b441390a22a6c4b35f274857ccb58de030d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273047"
---
# <a name="creatormap-structure"></a>CreatorMap 構造体

は、Windows ランタイム C++ テンプレートライブラリインフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
struct CreatorMap;
```

## <a name="remarks"></a>解説

オブジェクトを初期化、登録、および登録解除する方法について説明します。

`CreatorMap`には次の情報が含まれます。

- オブジェクトを初期化、登録、および登録解除する方法。

- 従来の COM または Windows ランタイムファクトリに応じてアクティベーションデータを比較する方法。

- インターフェイスのファクトリキャッシュとサーバー名に関する情報。

## <a name="members"></a>メンバー

### <a name="public-data-members"></a>パブリック データ メンバー

名前                                          | 説明
--------------------------------------------- | ------------------------------------------------------------------------------------------------------
[CreatorMap:: activationId](#activationid)     | クラシック COM クラス ID または Windows ランタイム名のいずれかで識別されるオブジェクト ID を表します。
[CreatorMap:: factoryCache](#factorycache)     | のファクトリキャッシュへのポインターを格納し `CreatorMap` ます。
[CreatorMap:: factoryCreator](#factorycreator) | 指定したのファクトリを作成し `CreatorMap` ます。
[CreatorMap:: serverName](#servername)         | のサーバー名を格納し `CreatorMap` ます。

## <a name="inheritance-hierarchy"></a>継承階層

`CreatorMap`

## <a name="requirements"></a>要件

**ヘッダー:** resource.h

**名前空間:** Microsoft:: WRL::D etails

## <a name="creatormapactivationid"></a><a name="activationid"></a> CreatorMap:: activationId

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
union {
   const IID* clsid;
   const wchar_t* (*getRuntimeName)();
} activationId;
```

### <a name="parameters"></a>パラメーター

*clsid*<br/>
インターフェイス ID。

*getRuntimeName*<br/>
オブジェクトの Windows ランタイム名を取得する関数。

### <a name="remarks"></a>解説

クラシック COM クラス ID または Windows ランタイム名のいずれかで識別されるオブジェクト ID を表します。

## <a name="creatormapfactorycache"></a><a name="factorycache"></a> CreatorMap:: factoryCache

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
FactoryCache* factoryCache;
```

### <a name="remarks"></a>解説

のファクトリキャッシュへのポインターを格納し `CreatorMap` ます。

## <a name="creatormapfactorycreator"></a><a name="factorycreator"></a> CreatorMap:: factoryCreator

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
HRESULT (*factoryCreator)(
   unsigned int* currentflags,
   const CreatorMap* entry,
   REFIID iidClassFactory,
IUnknown** factory);
```

### <a name="parameters"></a>パラメーター

*currentflags*<br/>
[RuntimeClassType](runtimeclasstype-enumeration.md)列挙子の1つ。

*キー*<br/>
CreatorMap。

*iidClassFactory*<br/>
クラスファクトリのインターフェイス ID。

*factory*<br/>
操作が完了したときに、クラスファクトリのアドレス。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

### <a name="remarks"></a>解説

指定した CreatorMap のファクトリを作成します。

## <a name="creatormapservername"></a><a name="servername"></a> CreatorMap:: serverName

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
const wchar_t* serverName;
```

### <a name="remarks"></a>解説

CreatorMap のサーバー名を格納します。
