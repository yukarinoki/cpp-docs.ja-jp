---
description: '詳細情報: &lt; cstdalign が&gt;'
title: '&lt;cstdalign が&gt;'
ms.date: 07/11/2019
f1_keywords:
- <cstdalign>
- __alignas_is_defined
- __alignof_is_defined
helpviewer_keywords:
- cstdalign header
- __alignas_is_defined
- __alignof_is_defined
ms.assetid: 9d570924-d299-4225-9a58-8c4c820f5903
ms.openlocfilehash: 7727f75ad0627c2a22b856631a776a2ee5426271
ms.sourcegitcommit: 118e4ad82c0f1c9ac120f105d84224e5fe4cef28
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "98126612"
---
# <a name="ltcstdaligngt"></a>&lt;cstdalign が&gt;

一部の C++ 標準ライブラリの実装では、このヘッダーに C 標準ライブラリヘッダーが含まれて \<stdalign.h> おり、関連する名前が名前空間に追加され `std` ます。 このヘッダーは MSVC に実装されていないため、 \<cstdalign> ヘッダーは互換性マクロ `__alignas_is_defined` およびを定義し `__alignof_is_defined` ます。

> [!NOTE]
> ヘッダーには \<stdalign.h> C++ のキーワードであるマクロが定義されているため、これを含めても効果はありません。 \<stdalign.h>ヘッダーは C++ では非推奨とされます。 \<cstdalign>ヘッダーは c++ 17 では非推奨とされており、Draft c++ 20 標準では削除されています。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<cstdalign>

**名前空間:** std

## <a name="macros"></a>マクロ

| マクロ | 説明 |
| - | - |
| `__alignas_is_defined` | 整数定数1に展開する C 互換マクロ。 |
| `__alignof_is_defined` | 整数定数1に展開する C 互換マクロ。 |

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](cpp-standard-library-header-files.md)\
[C++ 標準ライブラリの概要](cpp-standard-library-overview.md)\
[C++ 標準ライブラリのスレッドセーフ](thread-safety-in-the-cpp-standard-library.md)
