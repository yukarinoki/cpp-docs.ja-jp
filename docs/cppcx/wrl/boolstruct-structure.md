---
description: '次の詳細情報: Bool Struct 構造体'
title: BoolStruct 構造体
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::BoolStruct
- internal/Microsoft::WRL::Details::BoolStruct::Member
helpviewer_keywords:
- Microsoft::WRL::Details::BoolStruct structure
- Microsoft::WRL::Details::BoolStruct::Member data member
ms.assetid: 666eae78-e81d-4fb7-a9e4-1ba617d6d4cd
ms.openlocfilehash: d0c30f554cf2f7ebc3bfaf825b43dc28329f697e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338800"
---
# <a name="boolstruct-structure"></a>BoolStruct 構造体

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
struct BoolStruct;
```

## <a name="remarks"></a>解説

`BoolStruct`構造体は、 `ComPtr` がインターフェイスのオブジェクトの有効期間を管理しているかどうかを定義します。 `BoolStruct` は、 [ブール型 ()](comptr-class.md#operator-microsoft-wrl-details-booltype) 演算子によって内部的に使用されます。

## <a name="members"></a>メンバー

### <a name="public-data-members"></a>パブリック データ メンバー

名前                          | 説明
----------------------------- | ------------------------------------------------------------------------------------------------------------------
[Bool Struct:: Member](#member) | [Comptr](comptr-class.md)がインターフェイスのオブジェクトの有効期間を管理するかどうかを指定します。

## <a name="inheritance-hierarchy"></a>継承階層

`BoolStruct`

## <a name="requirements"></a>要件

**ヘッダー:** 内部 .h

**名前空間:** Microsoft:: WRL::D etails

## <a name="boolstructmember"></a><a name="member"></a> Bool Struct:: Member

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
int Member;
```

### <a name="remarks"></a>解説

[Comptr](comptr-class.md)がインターフェイスのオブジェクトの有効期間を管理するかどうかを指定します。
