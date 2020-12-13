---
description: '詳細情報: piecewise_contruct_t 構造'
title: piecewise_contruct_t 構造体
ms.date: 11/04/2016
f1_keywords:
- utility/std::piecewise_contruct_t
helpviewer_keywords:
- piecewise_contruct_t class
- piecewise_contruct_t structure
ms.openlocfilehash: 7fefacff75b47c25cb9ae07cc894498eadb551df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340750"
---
# <a name="piecewise_contruct_t-structure"></a>piecewise_contruct_t 構造体

構造体 `piecewise_construct_t` は、別のコンストラクターと関数のオーバーロードを維持するために使用される空の構造体型です。 具体的に `pair` は、には、最初の引数としてを持つコンストラクターがあり、 `piecewise_construct_t` その後に2つの引数があり `tuple` ます。

## <a name="syntax"></a>構文

```cpp
struct piecewise_construct_t { explicit piecewise_construct_t() = default; };

inline constexpr piecewise_construct_t piecewise_construct{};
```
