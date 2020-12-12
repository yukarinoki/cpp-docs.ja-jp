---
description: '詳細情報: &lt; ccomplex&gt;'
title: '&lt;ccomplex&gt;'
ms.date: 07/11/2019
f1_keywords:
- <ccomplex>
- ccomplex
helpviewer_keywords:
- ccomplex header
ms.assetid: a9fcb5f0-88e3-464b-a5fd-d1afb8cd7e6f
ms.openlocfilehash: d657d7b0b2a203bcbad93ff1c78f6b78eb4d7707
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325316"
---
# <a name="ltccomplexgt"></a>&lt;ccomplex&gt;

には、C++ 標準ライブラリヘッダーが含まれてい [\<complex>](complex.md) ます。

> [!NOTE]
> C 標準ライブラリ \<complex.h> ヘッダーは \<ccomplex> 、およびの C++ オーバーロードによって実質的に置き換えられるため、には含まれていません \<complex> \<cmath> 。 これにより、ヘッダーが冗長になり \<ccomplex> ます。 \<complex.h>ヘッダーは C++ では非推奨とされます。 \<ccomplex>ヘッダーは c++ 17 では非推奨とされており、Draft c++ 20 標準では削除されています。

## <a name="requirements"></a>要件

**ヘッダー:**\<ccomplex>

**名前空間:** std

## <a name="remarks"></a>解説

で宣言されている名前は、で宣言されて `clog` \<complex.h> いると `std` 競合する可能性があるため、名前空間で定義されていません `clog` [\<iostream>](iostream.md) 。

## <a name="see-also"></a>関連項目

[\<complex>](complex.md)\
[\<cmath>](cmath.md)\
[ヘッダーファイルのリファレンス](cpp-standard-library-header-files.md)\
[C++ 標準ライブラリの概要](cpp-standard-library-overview.md)\
[C++ 標準ライブラリのスレッドセーフ](thread-safety-in-the-cpp-standard-library.md)
