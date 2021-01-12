---
description: '詳細情報: &lt; ccomplex&gt;'
title: '&lt;ccomplex&gt;'
ms.date: 07/11/2019
f1_keywords:
- <ccomplex>
helpviewer_keywords:
- ccomplex header
ms.assetid: a9fcb5f0-88e3-464b-a5fd-d1afb8cd7e6f
ms.openlocfilehash: 6c9aa717031238681fa04bc20ab6ca93429553ec
ms.sourcegitcommit: 118e4ad82c0f1c9ac120f105d84224e5fe4cef28
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "98126677"
---
# <a name="ltccomplexgt"></a>&lt;ccomplex&gt;

には、C++ 標準ライブラリヘッダーが含まれてい [\<complex>](complex.md) ます。

> [!NOTE]
> C 標準ライブラリ \<complex.h> ヘッダーは \<ccomplex> 、およびの C++ オーバーロードによって実質的に置き換えられるため、には含まれていません \<complex> \<cmath> 。 これにより、ヘッダーが冗長になり \<ccomplex> ます。 \<complex.h>ヘッダーは C++ では非推奨とされます。 \<ccomplex>ヘッダーは c++ 17 では非推奨とされており、Draft c++ 20 標準では削除されています。

## <a name="requirements"></a>必要条件

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
