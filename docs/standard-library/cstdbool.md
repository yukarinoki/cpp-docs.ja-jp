---
description: '詳細情報: &lt; cstdbool&gt;'
title: '&lt;cstdbool&gt;'
ms.date: 07/11/2019
f1_keywords:
- <cstdbool>
helpviewer_keywords:
- cstdbool header
ms.assetid: 44ccb8b2-d808-4715-8097-58ba09ab33ed
ms.openlocfilehash: de36d4088c3494cf9b8efcf5175a527da7af8ece
ms.sourcegitcommit: 118e4ad82c0f1c9ac120f105d84224e5fe4cef28
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "98126599"
---
# <a name="ltcstdboolgt"></a>&lt;cstdbool&gt;

C 標準ライブラリヘッダーをインクルード \<stdbool.h> し、関連する名前を名前空間に追加し `std` ます。

> [!NOTE]
> ヘッダーには \<stdbool.h> C++ のキーワードであるマクロが定義されているため、これを含めても効果はありません。 \<stdbool.h>ヘッダーは C++ では非推奨とされます。 \<cstdbool>ヘッダーは c++ 17 では非推奨とされており、Draft c++ 20 標準では削除されています。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<cstdbool>

**名前空間:** std

## <a name="remarks"></a>解説

このヘッダーをインクルードすると、C 標準ライブラリヘッダーの外部リンケージを使用して宣言された名前が、名前空間で宣言され `std` ます。

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](cpp-standard-library-header-files.md)\
[C++ 標準ライブラリの概要](cpp-standard-library-overview.md)\
[C++ 標準ライブラリのスレッドセーフ](thread-safety-in-the-cpp-standard-library.md)
