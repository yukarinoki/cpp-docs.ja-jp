---
description: '詳細情報: open'
title: open
ms.date: 12/16/2019
api_name:
- open
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
- open
helpviewer_keywords:
- open function
ms.assetid: e3139118-4da2-434b-a551-fcf3fccf49b5
ms.openlocfilehash: 65dc30f24737e1071deedead78d0b8267e4de97b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195646"
---
# <a name="open"></a>open

Microsoft 実装の POSIX 関数名 `open` は、 [_open](open-wopen.md) 関数の非推奨のエイリアスです。 既定では、 [コンパイラの警告 (レベル 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)が生成されます。 名前は、実装固有の名前の標準 C 規則に従っていないため、非推奨とされます。 ただし、関数は引き続きサポートされます。

代わりに [_open](open-wopen.md) を使用することをお勧めします。 または、この関数名を引き続き使用して、警告を無効にすることもできます。 詳細については、「警告と[POSIX の関数名](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names)を[無効にする](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning)」を参照してください。
