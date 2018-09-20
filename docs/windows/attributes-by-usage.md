---
title: 使用法別の属性 |Microsoft Docs
ms.custom: index-page
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++/CLI]
ms.assetid: 8be2de10-b1ff-4ca4-a114-75318408593c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 875bc3163bc579c7d6da8055a0a24275e8be92a1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393855"
---
# <a name="attributes-by-usage"></a>使用法別の属性

このトピックでは、C++ 言語要素を適用するに従って属性を使用します。

属性に属性のスコープに含まれていない Visual C の要素が前にある場合は、属性ブロックがコメントとして扱われます。

|属性|説明|
|---------------|-----------------|
|[モジュール属性](../windows/module-attributes.md)|適用されます、[モジュール](../windows/module-cpp.md)属性。|
|[インターフェイス属性](../windows/interface-attributes.md)|適用されます、 [_ _interface](../cpp/interface.md) C++ のキーワード。|
|[クラス属性](../windows/class-attributes.md)|C++ のキーワードを適用します。|
|[メソッド属性](../windows/method-attributes.md)|クラス、コクラスまたはインターフェイスのメソッドに適用されます。|
|[パラメーター属性](../windows/parameter-attributes.md)|クラスまたはインターフェイスのメソッドのパラメーターに適用されます。|
|[データ メンバー属性](../windows/data-member-attributes.md)|クラス、コクラスまたはインターフェイス内のデータ メンバーに適用されます。|
|[Typedef、Enum、Union、および Struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)|C++ のキーワードを適用します。|
|[配列属性](../windows/array-attributes.md)|アレイに適用されるまたは`SAFEARRAY`s。|
|[スタンドアロン属性](../windows/stand-alone-attributes.md)|コード行のような動作をしますが、C++ のキーワードについては動作しません。 スタンドアロン属性ステートメントには、行の末尾にセミコロンが必要です。|
|[カスタム属性](../windows/custom-attributes-cpp.md)|メタデータを拡張できます。|

## <a name="see-also"></a>関連項目

[C++ 属性リファレンス](../windows/cpp-attributes-reference.md)<br/>
[概念](../windows/attributed-programming-concepts.md)<br/>
[グループ別の属性](../windows/attributes-by-group.md)<br/>
[属性リファレンス (アルファベット順)](../windows/attributes-alphabetical-reference.md)