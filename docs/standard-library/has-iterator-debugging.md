---
description: '詳細については、次を参照してください: _HAS_ITERATOR_DEBUGGING'
title: _HAS_ITERATOR_DEBUGGING
ms.date: 11/04/2016
f1_keywords:
- _HAS_ITERATOR_DEBUGGING
helpviewer_keywords:
- _HAS_ITERATOR_DEBUGGING
ms.assetid: 90077dbb-8a76-4963-83a6-29f4854007a8
ms.openlocfilehash: ee1765739624fe7c6fccd41ff84f455d5f90cc42
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231993"
---
# <a name="_has_iterator_debugging"></a>_HAS_ITERATOR_DEBUGGING

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) に置き換えられたこのマクロは、デバッグ ビルドで反復子のデバッグ機能を有効にするかどうかを定義します。 既定では、反復子のデバッグはデバッグ ビルドで有効になっており、製品版ビルドで無効になっています。 詳細については、「 [デバッグ反復子のサポート](../standard-library/debug-iterator-support.md)」を参照してください。

> [!IMPORTANT]
> _HAS_ITERATOR_DEBUGGING マクロを直接使用することは非推奨とされます。 代わりに、_ITERATOR_DEBUG_LEVEL を使用して反復子デバッグ設定を制御します。 詳細については、「[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)」を参照してください。

## <a name="remarks"></a>解説

デバッグビルドで反復子デバッグを有効にするには、_ITERATOR_DEBUG_LEVEL を2に設定します。 これは、_HAS_ITERATOR_DEBUGGING 設定が1であるか、有効になっていることと同じです。

```cpp
#define _ITERATOR_DEBUG_LEVEL 2
```

リテールビルドで _ITERATOR_DEBUG_LEVEL を2に設定することはできません (_HAS_ITERATOR_DEBUGGING を1に設定することはできません)。

デバッグビルドでデバッグ反復子を無効にするには、_ITERATOR_DEBUG_LEVEL を0または1に設定します。 これは、_HAS_ITERATOR_DEBUGGING 設定0または disabled と同じです。

```cpp
#define _ITERATOR_DEBUG_LEVEL 0
```

## <a name="see-also"></a>関連項目

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)\
[反復子のデバッグのサポート](../standard-library/debug-iterator-support.md)\
[チェックを行う反復子](../standard-library/checked-iterators.md)\
[安全なライブラリ: C++ 標準ライブラリ](../standard-library/safe-libraries-cpp-standard-library.md)
