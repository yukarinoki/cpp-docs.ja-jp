---
title: implementation_only |Microsoft Docs
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
ms.openlocfilehash: 2e7f0f40ad5d01b647f1f3273dc9a55d7cfa7564
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2018
ms.locfileid: "42540198"
---
# <a name="implementationonly"></a>implementation_only
**C++ 固有の仕様**  
  
.tlh ヘッダー ファイル (プライマリ ヘッダー ファイル) の生成を抑制します。  
  
## <a name="syntax"></a>構文  
  
```  
implementation_only  
```  
  
## <a name="remarks"></a>Remarks  
 
このファイルには、タイプ ライブラリ コンテンツを公開するために使用されているすべての宣言が含まれます。 ラッパー メンバー関数を実装した .tli ヘッダー ファイルが生成され、コンパイルに含められます。  
  
この属性の指定時には、.tli ヘッダーのコンテンツは .tlh ヘッダーで通常使用される同じ名前空間にあります。 また、メンバー関数はインライン関数として宣言されていません。  
  
**Implementation_only**属性と組み合わせて使用される、 [no_implementation](../preprocessor/no-implementation.md)プリコンパイル済みヘッダー (PCH) ファイルから、実装を保持するための手段として属性。 `#import` 属性を含む `no_implementation` ステートメントは、PCH の作成に使用されるソース領域に配置されます。 生成される PCH は、多数のソース ファイルによって使用されます。 `#import`ステートメントを**implementation_only** PCH 領域外部属性で使用されます。 いずれかのソース ファイルでこのステートメントを 1 回だけ使用する必要があります。 これによって、各ソース ファイルについて追加の再コンパイルを行う必要なく、すべてのラッパー メンバー関数が生成されます。  
  
> [!NOTE]
> **Implementation_only**いずれかで属性`#import`ステートメントは別と組み合わせて使用する必要があります`#import`ステートメントは、同じ型、ライブラリ、`no_implementation`属性。 それ以外の場合は、コンパイラ エラーが生成されます。 これは、ラッパー クラスの定義がによって生成されるため、`#import`ステートメントを`no_implementation`属性は、コンパイルによって生成された実装に必要な**implementation_only**属性。  
  
**END C 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 
[#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)