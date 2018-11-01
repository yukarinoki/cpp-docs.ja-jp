---
title: リンカ ツール エラー LNK1256
ms.date: 11/04/2016
f1_keywords:
- xml
- LNK1256
helpviewer_keywords:
- LNK1256
ms.assetid: 55b64b2b-a56b-436c-a55e-ec9c6dcb050e
ms.openlocfilehash: 9d969d1e5bbae92ed49747f761c1b89d1910d4e1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492867"
---
# <a name="linker-tools-error-lnk1256"></a>リンカ ツール エラー LNK1256

ALINK 処理に失敗しました : 理由

LNK1256 の一般的な理由は、アセンブリのバージョン番号が無効であることです。 値 65535 はアセンブリ バージョン番号のいずれの部分にも使用できません。 アセンブリのバージョンの有効な範囲は 0 ~ 65534 です。

また、指定されたキー コンテナーを ALINK が見つけることができなかった場合は、LNK1256 が発生する場合もあります。 キー コンテナーを削除し、再度追加する厳密な名前 CSP を使用して[Sn.exe (厳密名ツール)](/dotnet/framework/tools/sn-exe-strong-name-tool)します。

LNK1256 のもう 1 つの理由は、リンカーと Alink.dll の間でのバージョンの不一致です。 このことは、Visual Studio のインストールの破損によって発生する場合があります。 使用**プログラムと機能**修復または Visual Studio を再インストールする Windows コントロール パネルの します。

次の例では LNK1256 が生成されます。

```
// LNK1256.cpp
// compile with: /clr /LD
// LNK1256 expected
[assembly:System::Reflection::AssemblyVersionAttribute("1.0.65535")];
public class CMyClass {
public:
   int value;
};
```