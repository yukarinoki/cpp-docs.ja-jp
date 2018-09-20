---
title: Static Const Int リンケージのリテラル |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- literal attribute [C++]
- constants, declaring
- integral constant expressions
ms.assetid: d2a5e3d2-ffb0-4b61-8114-bec5993a1195
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c51853274b061ba290ff90993f45ccdf3375349b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46431295"
---
# <a name="static-const-int-linkage-is-no-longer-literal"></a>静的整数型定数リンケージの非リテラル化

クラスの定数のメンバーの宣言は、Visual c の C++ マネージ拡張から変更されました。

`static const`整数のメンバーはまだサポートされて、そのリンケージ属性が変更されました。 前者のリンケージ属性は、リテラル整数のメンバーで今すぐ実行されます。 たとえば、次のマネージ拡張クラスを考えてみます。

```
public __gc class Constants {
public:
   static const int LOG_DEBUG = 4;
};
```

これには、フィールド (リテラルの属性に注意してください) は CIL が基になる次の属性が生成されます。

```
.field public static literal int32
modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier) STANDARD_CLIENT_PRX = int32(0x00000004)
```

中に、これは、新しい構文で引き続きコンパイルされます。

```
public ref class Constants {
public:
   static const int LOG_DEBUG = 4;
};
```

リテラルの属性を出力し、したがって、ユーザーがいない表示定数として CLR ランタイム。

```
.field public static int32 modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier) STANDARD_CLIENT_PRX = int32(0x00000004)
```

同じ言語の間のリテラル属性を確保するために、宣言を変更する必要がありますに新しくサポートされた`literal`、次のように、データ メンバー

```
public ref class Constants {
public:
   literal int LOG_DEBUG = 4;
};
```

## <a name="see-also"></a>関連項目

[クラスまたはインターフェイス内でのメンバー宣言 (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)<br/>
[リテラル](../windows/literal-cpp-component-extensions.md)