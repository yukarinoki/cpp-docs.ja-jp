---
description: 詳細については、「implementation_only import 属性」を参照してください。
title: implementation_only インポート属性
ms.date: 08/29/2019
f1_keywords:
- implementation_only
helpviewer_keywords:
- implementation_only attribute
ms.assetid: d8cabc86-4425-45a0-9587-d57536980088
ms.openlocfilehash: 8afeb9981c5931596fc500419755521a41a3d7c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236543"
---
# <a name="implementation_only-import-attribute"></a>implementation_only インポート属性

**C++ 固有の仕様**

`.tlh`プライマリタイプライブラリヘッダーファイルの生成を抑制します。

## <a name="syntax"></a>構文

> **#import** *タイプライブラリ* **implementation_only**

## <a name="remarks"></a>解説

このファイルには、タイプ ライブラリ コンテンツを公開するために使用されているすべての宣言が含まれます。 `.tli`ラッパーメンバー関数の実装を含むヘッダーファイルが生成され、コンパイルに含まれます。

この属性が指定されている場合、 `.tli` ヘッダーの内容は、ヘッダーで通常使用されているものと同じ名前空間にあり `.tlh` ます。 また、メンバー関数はインライン関数として宣言されていません。

**Implementation_only** 属性は、プリコンパイル済みヘッダー (PCH) ファイルから実装を保持する手段として、 [no_implementation](../preprocessor/no-implementation.md)属性と組み合わせて使用することを目的としています。 `#import` 属性を含む `no_implementation` ステートメントは、PCH の作成に使用されるソース領域に配置されます。 生成される PCH は、多数のソース ファイルによって使用されます。 `#import`その後、 **implementation_only** 属性を持つステートメントが PCH 領域の外側で使用されます。 このステートメントは、いずれかのソースファイルで1回だけ使用する必要があります。 各ソースファイルに対して追加の再コンパイルを行わずに、必要なすべてのラッパーメンバー関数が生成されます。

> [!NOTE]
> 1つのステートメントの **implementation_only** 属性は、属性を使用して、 `#import` `#import` 同じタイプライブラリの別のステートメントと組み合わせて使用する必要があり `no_implementation` ます。 それ以外の場合は、コンパイラエラーが生成されます。 これは、属性を持つステートメントによって生成されたラッパークラス定義 `#import` `no_implementation` が、 **implementation_only** 属性によって生成された実装をコンパイルする必要があるためです。

**END C++ 固有の仕様**

## <a name="see-also"></a>関連項目

[#import 属性](../preprocessor/hash-import-attributes-cpp.md)\
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)
