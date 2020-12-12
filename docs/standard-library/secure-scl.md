---
description: '詳細については、次を参照してください: _SECURE_SCL'
title: _SECURE_SCL
ms.date: 11/04/2016
f1_keywords:
- _SECURE_SCL
helpviewer_keywords:
- _SECURE_SCL
ms.assetid: 4ffbc788-cc12-4c6a-8cd7-490081675086
ms.openlocfilehash: 1a0e32ada449709a60eb601138ce0bb8b7ae9123
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197102"
---
# <a name="_secure_scl"></a>_SECURE_SCL

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) に置き換えられています。このマクロは、[チェックを行う反復子](../standard-library/checked-iterators.md)を有効にするかどうかを定義します。 既定では、チェックを行う反復子はデバッグ ビルドで有効になっており、製品版ビルドで無効になっています。

> [!IMPORTANT]
> _SECURE_SCL マクロを直接使用することは非推奨とされます。 代わりに、_ITERATOR_DEBUG_LEVEL を使用して、チェックを行う反復子の設定を制御します。 詳細については、「[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)」を参照してください。

## <a name="remarks"></a>解説

チェックを行う反復子が有効になっている場合、反復子の安全でない使用によってランタイム エラーが発生し、プログラムが終了します。 チェックを行う反復子を有効にするには、_ITERATOR_DEBUG_LEVEL を1または2に設定します。 これは、_SECURE_SCL 設定が1であるか、有効になっていることと同じです。

```cpp
#define _ITERATOR_DEBUG_LEVEL 1
```

チェックを行う反復子を無効にするには、_ITERATOR_DEBUG_LEVEL を0に設定します。 これは、_SECURE_SCL 設定0または disabled と同じです。

```cpp
#define _ITERATOR_DEBUG_LEVEL 0
```

チェックを行う反復子に関する警告を無効にする方法の詳細については、「[_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md)」を参照してください。

## <a name="see-also"></a>関連項目

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)\
[チェックを行う反復子](../standard-library/checked-iterators.md)\
[反復子のデバッグのサポート](../standard-library/debug-iterator-support.md)\
[安全なライブラリ: C++ 標準ライブラリ](../standard-library/safe-libraries-cpp-standard-library.md)
