---
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
ms.openlocfilehash: 712c1f1638b954d1580eb527dd9eab7401917517
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317206"
---
# <a name="freelist-class"></a>freelist クラス

メモリ ブロックのリストを管理します。

## <a name="syntax"></a>構文

```cpp
template <std::size_t Sz, class Max>
class freelist : public Max
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Sz*|割り当てられる配列内の要素の数。|
|*最大*|フリー リストに格納される要素の最大数を示す最大クラス。 最大クラスは、[max_none](../standard-library/max-none-class.md)、[max_unbounded](../standard-library/max-unbounded-class.md)、[max_fixed_size](../standard-library/max-fixed-size-class.md)、[max_variable_size](../standard-library/max-variable-size-class.md) のいずれかにすることができます。|

## <a name="remarks"></a>解説

このクラス テンプレートは *、Max*で渡された max クラスによって決定されるリストの最大長を持つサイズ*Sz*のメモリ ブロックのリストを管理します。

### <a name="constructors"></a>コンストラクター

|Constructor|説明|
|-|-|
|[freelist](#freelist)|`freelist` 型のオブジェクトを構築します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[ポップ](#pop)|フリー リストから最初のメモリ ブロックを削除します。|
|[プッシュ](#push)|メモリ ブロックをリストに追加します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<allocators>

**名前空間:** stdext

## <a name="freelistfreelist"></a><a name="freelist"></a>フリーリスト::フリーリスト

`freelist` 型のオブジェクトを構築します。

```cpp
freelist();
```

### <a name="remarks"></a>解説

## <a name="freelistpop"></a><a name="pop"></a>フリーリスト::pop

フリー リストから最初のメモリ ブロックを削除します。

```cpp
void *pop();
```

### <a name="return-value"></a>戻り値

一覧から削除するメモリ ブロックへのポインターを返します。

### <a name="remarks"></a>解説

リストが空の場合、メンバー関数は NULL を返します。 それ以外の場合は、空き一覧から最初のメモリ ブロックを削除します。

## <a name="freelistpush"></a><a name="push"></a>フリーリスト::pウシュ

メモリ ブロックをリストに追加します。

```cpp
bool push(void* ptr);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Ptr*|フリー リストに追加するメモリ ブロックへのポインター。|

### <a name="return-value"></a>戻り値

max クラス`full`の関数が false を返す場合は**true、** false を返す場合は**false。** それ以外の`push`場合、関数は**false**を返します。

### <a name="remarks"></a>解説

max`full`クラスの関数が**false**を返す場合、このメンバー関数は *、ptr*が指すメモリ ブロックをリストの先頭に追加します。

## <a name="see-also"></a>関連項目

[\<アロケーター>](../standard-library/allocators-header.md)
