---
description: 詳細については、「引数アクセス」を参照してください。
title: 引数へのアクセス
ms.date: 04/04/2018
f1_keywords:
- c.arguments
helpviewer_keywords:
- argument access macros [C++]
- variable-length argument lists
ms.assetid: 7046ae34-a0ec-44f0-815d-3209492a3e19
ms.openlocfilehash: f62ac2bc4ae895afe763d0a0a4caa32601e82713
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221866"
---
# <a name="argument-access"></a>引数へのアクセス

**va_arg**、**va_end**、**va_start** の各マクロは、引数の数が可変である場合に、関数の引数へのアクセスを提供します。 これらのマクロは、 \<stdarg.h> ANSI/ISO C 互換の場合はで、 \<varargs.h> UNIX System V との互換性のためにはで定義されています。

## <a name="argument-access-macros"></a>引数アクセス マクロ

|マクロ|使用|
|-----------|-------------------------------|
|[va_arg](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|リストから引数を取得します|
|[va_end](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|ポインターをリセットします|
|[va_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|引数リストの先頭にポインターを設定します|

## <a name="see-also"></a>関連項目

[カテゴリ別ユニバーサル C ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)
