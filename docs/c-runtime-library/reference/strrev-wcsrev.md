---
description: 詳細については、「strrev、wcsrev」を参照してください。
title: strrev、wcsrev
ms.date: 12/16/2019
api_name:
- strrev
- wcsrev
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- strrev
- wcsrev
helpviewer_keywords:
- strrev function
- wcsrev function
ms.assetid: 89e05854-a9ce-4fb7-993d-a9831cd7edf2
ms.openlocfilehash: 2f9cb8e5a1a0bce09b0da030392d6b459f16c967
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209426"
---
# <a name="strrev-wcsrev"></a>strrev、wcsrev

Microsoft 固有の関数名 `strrev` と `wcsrev` は、 [_strrev および _wcsrev](strrev-wcsrev-mbsrev-mbsrev-l.md) 関数の非推奨のエイリアスです。 既定では、 [コンパイラの警告 (レベル 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)が生成されます。 これらの名前は、実装固有の名前の標準 C 規則に従っていないため、非推奨とされます。 ただし、関数は引き続きサポートされます。

代わりに [_strrev と _wcsrev](strrev-wcsrev-mbsrev-mbsrev-l.md) を使用することをお勧めします。 または、これらの関数名を引き続き使用して、警告を無効にすることもできます。 詳細については、「警告と[POSIX の関数名](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names)を[無効にする](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning)」を参照してください。
