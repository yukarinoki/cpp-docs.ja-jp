---
title: 追加の起動に関する考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- program startup [C++]
- startup code
- initializing before main
ms.assetid: 0e942aa6-8342-447c-b068-8980ed7622bd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c23f18a04010ba62d3651344464ff1668b2127d9
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405072"
---
# <a name="additional-startup-considerations"></a>起動に関するその他の考慮事項
C++ では、オブジェクトの構築時と破棄時にユーザー コードを実行することができます。 したがって、どの初期化に入る前に発生するかを理解しておく必要が`main`から出た後どのデストラクターが呼び出されると`main`します。 (詳細については、オブジェクトの構築と破棄は、次を参照してください[コンス トラクター](../cpp/constructors-cpp.md)と[デストラクター](../cpp/destructors-cpp.md)。)。  
  
 次の初期化に入る前に行われます`main`:  
  
-   静的データのゼロへの既定の初期化。 明示的な初期化子のないすべての静的データは、ランタイム初期化も含めて、他のコードを実行する前にゼロに設定されます。 その場合でも、静的データ メンバーは明示的に定義する必要があります。  
  
-   翻訳単位でのグローバルな静的オブジェクトの初期化。 これが発生するいずれかに入る前に`main`または任意の関数またはオブジェクトの翻訳単位内のオブジェクトを初めて使用する前にします。  
  
 **Microsoft 固有の仕様**  
  
 Microsoft C では、グローバルな静的オブジェクトに入る前に初期化される`main`します。  
  
 **Microsoft 固有の仕様はここまで**  
  
 相互依存しているのに翻訳単位が異なるグローバルな静的オブジェクトは、正しくない動作の原因になる可能性があります。  
  
## <a name="see-also"></a>関連項目  
 [起動と終了](../cpp/startup-and-termination-cpp.md)