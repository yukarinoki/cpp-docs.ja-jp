---
description: '詳細については、「方法: ネイティブ DLL をグローバルアセンブリキャッシュに追加する」を参照してください。'
title: '方法: ネイティブ DLL をグローバル アセンブリ キャッシュに追加する'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], native
- GAC (global assembly cache), loading native DLLs
- native DLLs [C++]
ms.assetid: 25e8d78a-b197-4269-b4e9-237a544ab3c8
ms.openlocfilehash: 267bc2f08fdd40da03b71222c48786ab7cc150fd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335408"
---
# <a name="how-to-add-native-dll-to-global-assembly-cache"></a>方法: ネイティブ DLL をグローバル アセンブリ キャッシュに追加する

(COM ではなく) ネイティブ DLL をグローバルアセンブリキャッシュに配置できます。

## <a name="example"></a>例

**/ASSEMBLYLINKRESOURCE** を使用すると、アセンブリにネイティブ DLL を埋め込むことができます。

詳細については、「 [/ASSEMBLYLINKRESOURCE (.NET Framework リソースへのリンク)](../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)」を参照してください。

```
/ASSEMBLYLINKRESOURCE:MyComponent.dll
```

## <a name="see-also"></a>関連項目

[C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)
