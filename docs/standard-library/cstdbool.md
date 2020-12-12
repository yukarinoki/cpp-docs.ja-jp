---
description: '詳細情報: &lt; cstdbool&gt;'
title: '&lt;cstdbool&gt;'
ms.date: 07/11/2019
f1_keywords:
- <cstdbool>
- cstdbool
helpviewer_keywords:
- cstdbool header
ms.assetid: 44ccb8b2-d808-4715-8097-58ba09ab33ed
ms.openlocfilehash: 0711c05ff136f90a701ff707976a172d2bcb1315
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324736"
---
# <a name="ltcstdboolgt"></a>&lt;cstdbool&gt;

C 標準ライブラリヘッダーをインクルード \<stdbool.h> し、関連する名前を名前空間に追加し `std` ます。

> [!NOTE]
> ヘッダーには \<stdbool.h> C++ のキーワードであるマクロが定義されているため、これを含めても効果はありません。 \<stdbool.h>ヘッダーは C++ では非推奨とされます。 \<cstdbool>ヘッダーは c++ 17 では非推奨とされており、Draft c++ 20 標準では削除されています。

## <a name="requirements"></a>要件

**ヘッダー:**\<cstdbool>

**名前空間:** std

## <a name="remarks"></a>解説

このヘッダーをインクルードすると、C 標準ライブラリヘッダーの外部リンケージを使用して宣言された名前が、名前空間で宣言され `std` ます。

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](cpp-standard-library-header-files.md)\
[C++ 標準ライブラリの概要](cpp-standard-library-overview.md)\
[C++ 標準ライブラリのスレッドセーフ](thread-safety-in-the-cpp-standard-library.md)
