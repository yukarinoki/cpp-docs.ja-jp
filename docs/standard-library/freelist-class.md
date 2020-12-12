---
description: '詳細情報: freelist クラス'
title: freelist クラス
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::freelist
- allocators/stdext::freelist::pop
- allocators/stdext::freelist::push
helpviewer_keywords:
- stdext::freelist
- stdext::freelist [C++], pop
- stdext::freelist [C++], push
ms.assetid: 8ad7e35c-4c80-4479-8ede-1a2497b06d71
ms.openlocfilehash: de0803aac13138dc25116084f52e7a5bea694b41
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324362"
---
# <a name="freelist-class"></a>freelist クラス

メモリ ブロックのリストを管理します。

## <a name="syntax"></a>構文

```cpp
template <std::size_t Sz, class Max>
class freelist : public Max
```

### <a name="parameters"></a>パラメーター

*Sz*\
割り当てられる配列内の要素の数。

*制限*\
フリー リストに格納される要素の最大数を示す最大クラス。 最大クラスは、[max_none](../standard-library/max-none-class.md)、[max_unbounded](../standard-library/max-unbounded-class.md)、[max_fixed_size](../standard-library/max-fixed-size-class.md)、[max_variable_size](../standard-library/max-variable-size-class.md) のいずれかにすることができます。

## <a name="remarks"></a>解説

このクラステンプレートは、size *Sz* のメモリブロックのリストを管理します。このリストの最大長は *、最大で* 渡されるクラスによって決定されます。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[freelist](#freelist)|`freelist` 型のオブジェクトを構築します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[ショート](#pop)|フリー リストから最初のメモリ ブロックを削除します。|
|[push](#push)|メモリ ブロックをリストに追加します。|

## <a name="requirements"></a>要件

**ヘッダー:**\<allocators>

**名前空間:** stdext

## <a name="freelistfreelist"></a><a name="freelist"></a> freelist:: freelist

`freelist` 型のオブジェクトを構築します。

```cpp
freelist();
```

### <a name="remarks"></a>解説

## <a name="freelistpop"></a><a name="pop"></a> freelist::p op

フリー リストから最初のメモリ ブロックを削除します。

```cpp
void *pop();
```

### <a name="return-value"></a>戻り値

一覧から削除するメモリ ブロックへのポインターを返します。

### <a name="remarks"></a>解説

このメンバー関数は、リストが空の場合、NULL を返します。 それ以外の場合は、空き一覧から最初のメモリ ブロックを削除します。

## <a name="freelistpush"></a><a name="push"></a> freelist::p u

メモリ ブロックをリストに追加します。

```cpp
bool push(void* ptr);
```

### <a name="parameters"></a>パラメーター

*ポインター*\
フリー リストに追加するメモリ ブロックへのポインター。

### <a name="return-value"></a>戻り値

**`true`**`full`max クラスの関数がを返す場合は **`false`** 。それ以外の場合、 `push` 関数はを返し **`false`** ます。

### <a name="remarks"></a>解説

`full`Max クラスの関数がを返す場合 **`false`** 、このメンバー関数は、 *ptr* が指すメモリブロックをリストの先頭に追加します。

## <a name="see-also"></a>関連項目

[\<allocators>](../standard-library/allocators-header.md)
