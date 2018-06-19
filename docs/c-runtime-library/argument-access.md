---
title: 引数へのアクセス | Microsoft Docs
ms.custom: ''
ms.date: 04/04/2018
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.arguments
dev_langs:
- C++
helpviewer_keywords:
- argument access macros [C++]
- variable-length argument lists
ms.assetid: 7046ae34-a0ec-44f0-815d-3209492a3e19
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 38d4031fcfba793a99688b6fd1cc91a3f1519989
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32387094"
---
# <a name="argument-access"></a>引数へのアクセス

**va_arg**、**va_end**、**va_start** の各マクロは、引数の数が可変である場合に、関数の引数へのアクセスを提供します。 これらのマクロは、ANSI/ISO C 互換の場合は \<stdarg.h> で、UNIX System V と互換性がある場合は \<varargs.h> で定義されています。

## <a name="argument-access-macros"></a>引数アクセス マクロ

|マクロ|使用|
|-----------|-------------------------------|
|[va_arg](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|リストから引数を取得します|
|[va_end](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|ポインターをリセットします|
|[va_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|引数リストの先頭にポインターを設定します|

## <a name="see-also"></a>関連項目

[カテゴリ別ユニバーサル C ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)
