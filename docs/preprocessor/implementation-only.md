---
title: implementation_only |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- implementation_only
dev_langs:
- C++
helpviewer_keywords:
- implementation_only attribute
ms.assetid: d8cabc86-4425-45a0-9587-d57536980088
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0a3a2cbf0b39dc1c5f5462ae105e2206d70a38f4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33912824"
---
# <a name="implementationonly"></a>implementation_only
**C 固有の仕様**  
  
 .tlh ヘッダー ファイル (プライマリ ヘッダー ファイル) の生成を抑制します。  
  
## <a name="syntax"></a>構文  
  
```  
implementation_only  
```  
  
## <a name="remarks"></a>コメント  
 このファイルには、タイプ ライブラリ コンテンツを公開するために使用されているすべての宣言が含まれます。 ラッパー メンバー関数を実装した .tli ヘッダー ファイルが生成され、コンパイルに含められます。  
  
 この属性の指定時には、.tli ヘッダーのコンテンツは .tlh ヘッダーで通常使用される同じ名前空間にあります。 また、メンバー関数はインライン関数として宣言されていません。  
  
 `implementation_only`属性と組み合わせて使用される、 [no_implementation](../preprocessor/no-implementation.md)プリコンパイル済みヘッダー (PCH) ファイルから、実装を保持するための手段として属性。 `#import` 属性を含む `no_implementation` ステートメントは、PCH の作成に使用されるソース領域に配置されます。 生成される PCH は、多数のソース ファイルによって使用されます。 これによって、`#import` 属性を含む `implementation_only` ステートメントが PCH 領域の外部で使用されます。 いずれかのソース ファイルでこのステートメントを 1 回だけ使用する必要があります。 これによって、各ソース ファイルについて追加の再コンパイルを行う必要なく、すべてのラッパー メンバー関数が生成されます。  
  
> [!NOTE]
>  1 つの `implementation_only` ステートメントで `#import` 属性を使用し、同時に `#import` 属性を含む同じタイプ ライブラリの別の `no_implementation` ステートメントを使用する必要があります。 それ以外の場合は、コンパイラ エラーが生成されます。 これは、`#import` 属性を含む `no_implementation` ステートメントによって生成されたラッパー クラス定義が、`implementation_only` 属性によって生成された実装をコンパイルするために必要であるためです。  
  
 **END C 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 [#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)