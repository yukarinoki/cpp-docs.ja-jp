---
title: 引数へのアクセス
ms.date: 04/04/2018
f1_keywords:
- c.arguments
helpviewer_keywords:
- argument access macros [C++]
- variable-length argument lists
ms.assetid: 7046ae34-a0ec-44f0-815d-3209492a3e19
ms.openlocfilehash: 8107cffa6a2da41c38b116b2e3fe36adf6ac945f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50470409"
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
