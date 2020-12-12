---
description: 詳細については、「オーバーライド指定子 (C++/CLI および C++/CX)」を参照してください。
title: オーバーライド指定子 (C++/CLI および C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- override specifiers, C++
- override specifiers
ms.assetid: 155bbf6f-4722-4654-afb1-9cb52af799fb
ms.openlocfilehash: ce0b9ad4464eef66bc71826825e8129ef0a24cab
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257590"
---
# <a name="override-specifiers--ccli-and-ccx"></a>オーバーライド指定子 (C++/CLI および C++/CX)

*オーバーライド指定子* は、継承された型および継承された型のメンバーの派生型での動作を変更します。

## <a name="all-runtimes"></a>すべてのランタイム

### <a name="remarks"></a>解説

オーバーライド指定子の詳細については、以下を参照してください。

- [abstract](abstract-cpp-component-extensions.md)

- [new (vtable の新しいスロット)](new-new-slot-in-vtable-cpp-component-extensions.md)

- [override](override-cpp-component-extensions.md)

- [sealed](sealed-cpp-component-extensions.md)

- [オーバーライド指定子とネイティブ コンパイル](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)

**abstract** と **sealed** は型宣言でも有効ですが、その場合はオーバーライド指定子として機能しません。

基底クラスの関数を明示的にオーバーライドする方法については、「[Explicit Overrides (明示的なオーバーライド)](explicit-overrides-cpp-component-extensions.md)」を参照してください。

## <a name="windows-runtime"></a>Windows ランタイム

(この言語機能には Windows ランタイムのみに適用される特記事項がありません。)

### <a name="requirements"></a>要件

コンパイラ オプション: `/ZW`

## <a name="common-language-runtime"></a>共通言語ランタイム

(この言語機能には共通言語ランタイムのみに適用される特記事項がありません。)

### <a name="requirements"></a>要件

コンパイラ オプション: `/clr`

## <a name="see-also"></a>関連項目

[.NET および UWP 用のコンポーネントの拡張機能](component-extensions-for-runtime-platforms.md)
