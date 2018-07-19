---
title: コンパイラ エラー C2026 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2026
dev_langs:
- C++
helpviewer_keywords:
- C2026
ms.assetid: 8e64b6e1-b967-479b-be97-d12dc4a8e389
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6b2952daa8cc7b3642cca5ba278990fde7d1ebe
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33167666"
---
# <a name="compiler-error-c2026"></a>コンパイラ エラー C2026
文字列が大きすぎるため、末尾の文字は切り捨てられます  
  
 文字列で 16380 1 バイト文字の制限を超えていました。  
  
 隣接する文字列の連結された場合、前に、文字列はで 16380 1 バイト文字より長くすることはできません。  
  
 この長さが約 50% の Unicode 文字列もこのエラーを生成します。  
  
 次のように定義された文字列があれば、C2026 が生成されます。  
  
```  
char sz[] =  
"\  
imagine a really, really \  
long string here\  
";  
```  
  
 分割できますとおり。  
  
```  
char sz[] =  
"\  
imagine a really, really "  
"long string here\  
";  
```  
  
 カスタム リソースまたは外部ファイルで非常に大きな文字列リテラル (32 K 以上) を格納することがあります。 参照してください[新しいカスタム リソースまたはデータ リソースを作成する](../../windows/creating-a-new-custom-or-data-resource.md)詳細についてはします。