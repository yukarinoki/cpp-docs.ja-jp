---
title: _HAS_ITERATOR_DEBUGGING | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- _HAS_ITERATOR_DEBUGGING
dev_langs:
- C++
helpviewer_keywords:
- _HAS_ITERATOR_DEBUGGING
ms.assetid: 90077dbb-8a76-4963-83a6-29f4854007a8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 81f0509c6230020b586c0341e1de608981c05476
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38965980"
---
# <a name="hasiteratordebugging"></a>_HAS_ITERATOR_DEBUGGING

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) に置き換えられたこのマクロは、デバッグ ビルドで反復子のデバッグ機能を有効にするかどうかを定義します。 既定では、反復子のデバッグはデバッグ ビルドで有効になっており、製品版ビルドで無効になっています。 詳細については、「[反復子のデバッグのサポート](../standard-library/debug-iterator-support.md)」を参照してください。

> [!IMPORTANT]
> _HAS_ITERATOR_DEBUGGING マクロの直接的な使用は非推奨とされます。 代わりに、反復子デバッグ設定を制御する _ITERATOR_DEBUG_LEVEL を使用します。 詳細については、「[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)」を参照してください。

## <a name="remarks"></a>Remarks

反復子のデバッグ ビルドでデバッグを有効にするには、2 に _ITERATOR_DEBUG_LEVEL を設定します。 これは、_HAS_ITERATOR_DEBUGGING 設定が 1 に相当または有効になっています。

```cpp
#define _ITERATOR_DEBUG_LEVEL 2
```

_ITERATOR_DEBUG_LEVEL を 2 に設定することはできません (および _HAS_ITERATOR_DEBUGGING を 1 に設定することはできません) 製品版ビルドでします。

デバッグ ビルドでデバッグ反復子を無効にするには、0 または 1 _ITERATOR_DEBUG_LEVEL を設定します。 これは 0、_HAS_ITERATOR_DEBUGGING 設定に相当または無効になっています。

```cpp
#define _ITERATOR_DEBUG_LEVEL 0
```

## <a name="see-also"></a>関連項目

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)<br/>
[Debug Iterator Support](../standard-library/debug-iterator-support.md)<br/>
[Checked Iterators](../standard-library/checked-iterators.md)<br/>
[安全なライブラリ: C++ 標準ライブラリ](../standard-library/safe-libraries-cpp-standard-library.md)<br/>
