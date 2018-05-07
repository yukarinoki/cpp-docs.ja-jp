---
title: コンパイラ エラー C2030 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2030
dev_langs:
- C++
helpviewer_keywords:
- C2030
ms.assetid: 5806cead-64df-4eff-92de-52c9a3f5ee62
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ceccc1088e32382167e7e6400360b30de07fde1d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2030"></a>コンパイラ エラー C2030
アクセシビリティが 'protected private' であるデストラクターは、'sealed' として宣言されたクラスのメンバーになることはできません  
  
 `sealed` として宣言された Windows ランタイム クラスは、protected private デストラクターを持つことはできません。 sealed 型では、パブリック仮想デストラクターとプライベート非仮想デストラクターだけが許可されています。 詳細については、次を参照してください。 [Ref クラスと構造体](../../cppcx/ref-classes-and-structs-c-cx.md)です。  
  
 このエラーを解決するには、デストラクターのアクセシビリティを変更します。