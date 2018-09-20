---
title: 値の型とその動作 (C +/cli CLI) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- value types
ms.assetid: 5cb872a6-1e0a-429d-853d-df4ab47e8f2a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4d2d980e48a6f948c35faf0c4e42969795ef8dc7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404658"
---
# <a name="value-types-and-their-behaviors-ccli"></a>値型とその動作 (C++/CLI)

値の型は、Visual c の C++ マネージ拡張からさまざまな方法に変更されました。 このセクションで、CLR 列挙型および値クラス型のボックス化と、CLR ヒープ上のボックス化されたインスタンスへのアクセスと内部ポインターと固定ポインターを見てと共にに注目します。 この領域で広範な言語の変更が発生しました。

## <a name="in-this-section"></a>このセクションの内容

[CLR 列挙型](../dotnet/value-types-and-their-behaviors-cpp-cli.md)<br/>
宣言と列挙型の動作の変更について説明します。

[値型の暗黙のボックス化](../dotnet/implicit-boxing-of-value-types.md)<br/>
値型と動作の結果として生じる変更の暗黙的なボックス化の動機について説明します。

[追跡ハンドルからボックス化変換された値へ](../dotnet/a-tracking-handle-to-a-boxed-value.md)<br/>
暗黙的なボックス化をについて説明します。 値のボックス化されたオブジェクトへの追跡ハンドルに値の型が変換されます。

[値型セマンティクス](../dotnet/value-type-semantics.md)<br/>
継承された仮想メソッド、クラスの既定のコンス トラクター、内部ポインターは、固定ポインターなど、値型セマンティクスの変更について説明します。

## <a name="see-also"></a>関連項目

[C++/CLI 移行ガイド](../dotnet/cpp-cli-migration-primer.md)<br/>
[クラスと構造体](../windows/classes-and-structs-cpp-component-extensions.md)