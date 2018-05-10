---
title: マネージ型 (C++ CL) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- __gc types
- types [C++], CLR
ms.assetid: 1ddd114e-be02-4de7-a4dd-a2d72ad8ff81
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 42426c45f4b8caf3cd4cb61ee867470dc9ea639f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="managed-types-ccl"></a>マネージ型 (C++/CL)
これらの型のオブジェクトの使用とマネージ型と作成の宣言の構文が大幅に変更されましたマネージ拡張から C++ の Visual c。 これは、ISO C 型システム内の統合を促進します。 これらの変更は、次のサブセクションで詳細に表示されます。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [マネージ クラス型の宣言](../dotnet/declaration-of-a-managed-class-type.md)  
 マネージ宣言する方法について説明`class`、 `struct`、または`interface`です。  
  
 [CLR 参照クラスのオブジェクトの宣言](../dotnet/declaration-of-a-clr-reference-class-object.md)  
 追跡ハンドルを使用して、参照クラスの型のオブジェクトを宣言する方法について説明します。  
  
 [CLR 配列の宣言](../dotnet/declaration-of-a-clr-array.md)  
 宣言および配列を初期化する方法について説明します。  
  
 [コンストラクターの初期化処理の順序における変更](../dotnet/changes-in-constructor-initialization-order.md)  
 クラスのコンス トラクターの初期化順序キーの変更について説明します。  
  
 [デストラクターのセマンティクスの変更](../dotnet/changes-in-destructor-semantics.md)  
 非確定的な終了処理について説明します`Finalize`と`Dispose`、参照オブジェクトとの明示的な影響を及ぼす可能性`Finalize`です。  
  
 **注:** まで延期されるデリゲートの詳細については、[デリゲートとイベント](../dotnet/delegates-and-events.md)の一般的なトピック、クラス内のイベント メンバーを表示するために[クラスまたはインターフェイス内でメンバーの宣言(C + + CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md).  
  
## <a name="see-also"></a>関連項目  
 [C + +/CLI 移行ガイド](../dotnet/cpp-cli-migration-primer.md)   
 [クラスと構造体](../windows/classes-and-structs-cpp-component-extensions.md)   
 [配列](../windows/arrays-cpp-component-extensions.md)