---
title: インライン アセンブリでの型と変数サイズ
ms.date: 08/30/2018
ms.topic: reference
helpviewer_keywords:
- variables, length
- size, getting in inline assembly
- size
- LENGTH operator
- TYPE operator
- SIZE operator
- inline assembly, operators
- variables, type
- variables, size
ms.assetid: b62c2f2b-a7ad-4145-bae4-d890db86d348
ms.openlocfilehash: cdb8bddccbea0ef711cb0be4bbac60f7457c625c
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79441568"
---
# <a name="type-and-variable-sizes-in-inline-assembly"></a>インライン アセンブリでの型と変数サイズ

**Microsoft 固有の仕様**

**長さ**、**サイズ**、および**型**の演算子の意味は、インラインアセンブリでは制限されています。 `DUP` 演算子では使用できません (MASM ディレクティブや演算子を使用してデータを定義することはできません)。 ただし、これらの値を使用して、C またC++は変数または型のサイズを調べることができます。

- **LENGTH**演算子は、配列内の要素の数を返すことができます。 配列でない変数の場合値 1 を返します。

- **Size**演算子は、C またはC++変数のサイズを返すことができます。 変数のサイズは、その**長さ**と**型**の積です。

- **型**演算子は、C C++型、型、または変数のサイズを返すことができます。 変数が配列の場合、 **TYPE**は配列の1つの要素のサイズを返します。

たとえば、プログラムに8要素の**int**配列が含まれているとします。

```cpp
int arr[8];
```

次の C およびアセンブリ式は、`arr` とその要素のサイズを生成します。

|__asm|C|サイズ|
|-------------|-------|----------|
|**長さ**arr|`sizeof`(arr)/`sizeof`(arr [0])|8|
|**サイズ**arr|`sizeof`(arr)|32|
|**「** Arr」と入力します。|`sizeof`(arr [0])|4|

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[__asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>