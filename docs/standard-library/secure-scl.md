---
title: _SECURE_SCL | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- _SECURE_SCL
dev_langs:
- C++
helpviewer_keywords:
- _SECURE_SCL
ms.assetid: 4ffbc788-cc12-4c6a-8cd7-490081675086
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f6a9fa05a4cb8c421a511a30fd62310d69003fde
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38966434"
---
# <a name="securescl"></a>_SECURE_SCL

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) に置き換えられています。このマクロは、[チェックを行う反復子](../standard-library/checked-iterators.md)を有効にするかどうかを定義します。 既定では、チェックを行う反復子はデバッグ ビルドで有効になっており、製品版ビルドで無効になっています。

> [!IMPORTANT]
> _SECURE_SCL マクロの直接的な使用は非推奨とされます。 代わりに、コントロールを使用して _ITERATOR_DEBUG_LEVEL は反復子の設定を確認します。 詳細については、「[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)」を参照してください。

## <a name="remarks"></a>Remarks

チェックを行う反復子が有効になっている場合、反復子の安全でない使用によってランタイム エラーが発生し、プログラムが終了します。 Checked 反復子を有効にするには、1 または 2 に _ITERATOR_DEBUG_LEVEL を設定します。 これは、1 の _SECURE_SCL 設定に相当または有効になっています。

```cpp
#define _ITERATOR_DEBUG_LEVEL 1
```

Checked 反復子を無効にするには、_ITERATOR_DEBUG_LEVEL を 0 に設定します。 これは 0、_SECURE_SCL 設定に相当または無効になっています。

```cpp
#define _ITERATOR_DEBUG_LEVEL 0
```

チェックを行う反復子に関する警告を無効にする方法の詳細については、「[_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md)」を参照してください。

## <a name="see-also"></a>関連項目

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)<br/>
[Checked Iterators](../standard-library/checked-iterators.md)<br/>
[Debug Iterator Support](../standard-library/debug-iterator-support.md)<br/>
[安全なライブラリ: C++ 標準ライブラリ](../standard-library/safe-libraries-cpp-standard-library.md)<br/>
