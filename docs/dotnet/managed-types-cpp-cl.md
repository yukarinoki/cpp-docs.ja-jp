---
title: マネージ型 (C++-CL) |Microsoft Docs
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
ms.openlocfilehash: 382228b9e8364d90d7929b4633744071c5eb0c77
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46408040"
---
# <a name="managed-types-ccl"></a>マネージド型 (C++/CL)

これらの型のオブジェクトの使用と管理対象の種類と作成の宣言の構文が大幅に変更されましたマネージ拡張から C++ 用 Visual c。 これは、ISO C の型システム内での統合を促進します。 これらの変更は、次のサブセクションで詳しく表示されます。

## <a name="in-this-section"></a>このセクションの内容

[マネージド クラス型の宣言](../dotnet/declaration-of-a-managed-class-type.md)<br/>
マネージ宣言する方法について説明します`class`、 `struct`、または`interface`します。

[CLR 参照クラスのオブジェクトの宣言](../dotnet/declaration-of-a-clr-reference-class-object.md)<br/>
追跡ハンドルを使用して、参照クラス型のオブジェクトを宣言する方法について説明します。

[CLR 配列の宣言](../dotnet/declaration-of-a-clr-array.md)<br/>
宣言および配列を初期化する方法について説明します。

[コンストラクターの初期化処理の順序における変更](../dotnet/changes-in-constructor-initialization-order.md)<br/>
クラス コンス トラクターの初期化順序キーの変更について説明します。

[デストラクターのセマンティクスの変更](../dotnet/changes-in-destructor-semantics.md)<br/>
非確定的な終了処理について説明します`Finalize`と`Dispose`、オブジェクトの参照との明示的な使用の影響`Finalize`します。

**注:** デリゲートの説明がまで延期[デリゲートとイベント](../dotnet/delegates-and-events.md)クラスの一般的なトピック内のイベント メンバーを提示するために[クラスまたはインターフェイス内でメンバーの宣言(C +/CLI CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md).

## <a name="see-also"></a>関連項目

[C++/CLI 移行ガイド](../dotnet/cpp-cli-migration-primer.md)<br/>
[クラスと構造体](../windows/classes-and-structs-cpp-component-extensions.md)<br/>
[配列](../windows/arrays-cpp-component-extensions.md)