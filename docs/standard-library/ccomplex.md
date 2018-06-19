---
title: '&lt;ccomplex&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <ccomplex>
dev_langs:
- C++
ms.assetid: a9fcb5f0-88e3-464b-a5fd-d1afb8cd7e6f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: de5c67fc88da6fc4674b7dad67b5f74dcc3ce54d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33850386"
---
# <a name="ltccomplexgt"></a>&lt;ccomplex&gt;

C++ 標準ライブラリ ヘッダー [\<complex>](../standard-library/complex.md) をインクルードします。これにより、標準 C ライブラリ ヘッダー \<complex.h> がインクルードされ、関連する名前が `std` 名前空間に追加されます。

## <a name="syntax"></a>構文

```cpp
#include <ccomplex>

```

## <a name="remarks"></a>コメント

このヘッダーをインクルードすると、標準 C ライブラリ ヘッダーの外部リンケージで宣言された名前が、`std` 名前空間でも宣言されます。

\<complex.h> で宣言される名前 `clog` は `std` 名前空間に定義されていません。これは、[\<iostream>](../standard-library/iostream.md) で宣言されている `clog` と競合する可能性があるためです。

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリの概要](../standard-library/cpp-standard-library-overview.md)<br/>
