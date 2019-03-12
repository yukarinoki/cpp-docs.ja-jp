---
title: '方法: ネイティブ DLL をグローバル アセンブリ キャッシュに追加します。'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], native
- GAC (global assembly cache), loading native DLLs
- native DLLs [C++]
ms.assetid: 25e8d78a-b197-4269-b4e9-237a544ab3c8
ms.openlocfilehash: b4b886dfef3185c1b3084ed02abcef1ad2630c11
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2019
ms.locfileid: "57746488"
---
# <a name="how-to-add-native-dll-to-global-assembly-cache"></a>方法: ネイティブ DLL をグローバル アセンブリ キャッシュに追加します。

ネイティブ DLL (COM 以外) は、グローバル アセンブリ キャッシュに配置できます。

## <a name="example"></a>例

**/ASSEMBLYLINKRESOURCE**ネイティブ DLL をアセンブリに埋め込むことができます。

詳細については、「[/ASSEMBLYLINKRESOURCE (.NET Framework リソースへのリンク)](../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)」を参照してください。

```
/ASSEMBLYLINKRESOURCE:MyComponent.dll
```

## <a name="see-also"></a>関連項目

[C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)
