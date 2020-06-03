---
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
ms.openlocfilehash: 4f2a5acf6edb824cff2121c1b6444181b5cfcf98
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371852"
---
# <a name="boolstruct-structure"></a>BoolStruct 構造体

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
struct BoolStruct;
```

## <a name="remarks"></a>解説

構造体`BoolStruct`は、インターフェイスの`ComPtr`オブジェクトの有効期間を管理するかどうかを定義します。 `BoolStruct`は[、BoolType()](comptr-class.md#operator-microsoft-wrl-details-booltype)演算子によって内部的に使用されます。

## <a name="members"></a>メンバー

### <a name="public-data-members"></a>パブリック データ メンバー

名前                          | 説明
----------------------------- | ------------------------------------------------------------------------------------------------------------------
[ブール構造体:メンバー](#member) | [ComPtr](comptr-class.md)がインターフェイスのオブジェクトの有効期間を管理していることを指定します。

## <a name="inheritance-hierarchy"></a>継承階層

`BoolStruct`

## <a name="requirements"></a>必要条件

**ヘッダー:** 内部.h

**名前空間:** マイクロソフト::WRL::Dのテール

## <a name="boolstructmember"></a><a name="member"></a>ブール構造体:メンバー

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
int Member;
```

### <a name="remarks"></a>解説

[ComPtr](comptr-class.md)がインターフェイスのオブジェクトの有効期間を管理していることを指定します。
