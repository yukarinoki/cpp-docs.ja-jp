---
title: 転送の型 (C +/cli CLI) |Microsoft Docs
ms.custom: ''
ms.date: 10/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- type forwarding, C++
ms.assetid: ae730b69-0c27-41cc-84e1-3132783866ea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7fe70de2503134bf76f5e1c7099773737cc153f8
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2018
ms.locfileid: "49328338"
---
# <a name="type-forwarding-ccli"></a>型の転送 (C++/CLI)

*型転送*ことなど、アセンブリ A を使用するクライアントを再コンパイルする必要はありませんは、別のアセンブリ (アセンブリ B) に 1 つのアセンブリ (アセンブリ A) から型を移動することができます

## <a name="windows-runtime"></a>Windows ランタイム

この機能は、Windows ランタイムでサポートされていません。

## <a name="common-language-runtime"></a>共通言語ランタイム

次のコード例では、型の転送を使用する方法を示します。

### <a name="syntax"></a>構文

```cpp
#using "new.dll"
[assembly:TypeForwardedTo(type::typeid)];
```

### <a name="parameters"></a>パラメーター

*new*<br/>
型定義の移動先のアセンブリ。

*type*<br/>
型の定義を別のアセンブリに移動します。

### <a name="remarks"></a>Remarks

コンポーネント (アセンブリ) が付属し、後にクライアント アプリケーションで使用されていることができますを使用する型のコンポーネント (アセンブリ) から別のアセンブリに型を移動、更新されたコンポーネント (および必要な追加のアセンブリ) を出荷する転送とクライアントアプリケーションは再コンパイルされることがなく機能します。

型の転送は、既存のアプリケーションによって参照されるコンポーネントに対してのみ機能します。 アプリケーションを再構築するときは、アプリケーションで使用されている型の適切なアセンブリ参照が必要があります。

追加する必要がありますアセンブリから型 (タイプ A) を転送するときに、`TypeForwardedTo`アセンブリ参照と、その型の属性。 参照されているアセンブリには、次のいずれかを含める必要があります。

- タイプ a の定義

- A`TypeForwardedTo`アセンブリ参照と同様に、A の種類の属性。

転送可能な型の例は次のとおりです。

- ref クラス

- 値クラス

- 列挙型

- インターフェイス

次の種類を転送することはできません。

- ジェネリック型

- ネイティブ型

- 入れ子にされた型 (入れ子にされた型を転送する場合は、転送することはそれを囲む型)

型は、共通言語ランタイムを対象とする任意の言語で作成されたアセンブリを転送できます。

アセンブリ A.dll をビルドするために使用するソース コード ファイルには、型定義が含まれている場合、(`ref class MyClass`)、その型の移動を必要として B.dll のアセンブリに定義の場合します。

1. 移動、 `MyClass` B.dll を構築するために使用するソース コード ファイルに定義を入力します。

2. B.dll アセンブリをビルドします。

3. 削除、`MyClass`種類の定義から、ソース コードの使用を A.dll をビルドし、次に置き換えます。

    ```cpp
    #using "B.dll"
    [assembly:TypeForwardedTo(MyClass::typeid)];
    ```

4. アセンブリ A.dll をビルドします。

5. クライアント アプリケーションを再コンパイルしなくても、A.dll を使用します。

### <a name="requirements"></a>要件

コンパイラ オプション: `/clr`