---
title: '&lt;ccomplex&gt;'
ms.date: 11/04/2016
f1_keywords:
- <ccomplex>
ms.assetid: a9fcb5f0-88e3-464b-a5fd-d1afb8cd7e6f
ms.openlocfilehash: ab9e95eb7b432a85a75d73d388ec069b0d04ac62
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2018
ms.locfileid: "51517203"
---
# <a name="ltccomplexgt"></a>&lt;ccomplex&gt;

C++ 標準ライブラリ ヘッダー [\<complex>](../standard-library/complex.md) をインクルードします。これにより、標準 C ライブラリ ヘッダー \<complex.h> がインクルードされ、関連する名前が `std` 名前空間に追加されます。

## <a name="syntax"></a>構文

```cpp
#include <ccomplex>
```

## <a name="remarks"></a>Remarks

このヘッダーをインクルードすると、標準 C ライブラリ ヘッダーの外部リンケージで宣言された名前が、`std` 名前空間でも宣言されます。

\<complex.h> で宣言される名前 `clog` は `std` 名前空間に定義されていません。これは、[\<iostream>](../standard-library/iostream.md) で宣言されている `clog` と競合する可能性があるためです。

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリの概要](../standard-library/cpp-standard-library-overview.md)<br/>
