---
description: '詳細情報: identity 構造'
title: identity 構造体
ms.date: 11/04/2016
f1_keywords:
- utility/std::identity
helpviewer_keywords:
- identity class
- identity structure
ms.assetid: 990756fd-7969-4b39-ad7e-0878e8dac8fd
ms.openlocfilehash: 753a3b697eb2a77dd102f681403fd23d7062cb36
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231759"
---
# <a name="identity-structure"></a>identity 構造体

テンプレート パラメーターの型定義を指定する構造体。

## <a name="syntax"></a>構文

```cpp
struct identity {
   typedef Type type;
   Type operator()(const Type& left) const;
};
```

### <a name="parameters"></a>パラメーター

*左側*\
指定する値。

## <a name="remarks"></a>解説

このクラスにはパブリック型の定義 `type` が含まれています。これは、テンプレート パラメーターの型と同じです。 必要な型が関数パラメーターに設定されるようにするには、テンプレート関数 [forward](../standard-library/utility-functions.md#forward) と組み合わせて使用します。

以前のコードとの互換性を維持するために、クラスは `operator()` 引数を *左* に返す id 関数も定義します。
