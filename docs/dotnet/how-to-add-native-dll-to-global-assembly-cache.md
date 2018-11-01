---
title: '方法: ネイティブ DLL をグローバル アセンブリ キャッシュに追加する'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], native
- GAC (global assembly cache), loading native DLLs
- native DLLs [C++]
ms.assetid: 25e8d78a-b197-4269-b4e9-237a544ab3c8
ms.openlocfilehash: 1b11ebfae704ca1529113a00b463df728c85fe60
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641364"
---
# <a name="how-to-add-native-dll-to-global-assembly-cache"></a>方法: ネイティブ DLL をグローバル アセンブリ キャッシュに追加する

ネイティブ DLL (COM 以外) は、グローバル アセンブリ キャッシュに配置できます。

## <a name="example"></a>例

**/ASSEMBLYLINKRESOURCE**ネイティブ DLL をアセンブリに埋め込むことができます。

詳細については、「[/ASSEMBLYLINKRESOURCE (.NET Framework リソースへのリンク)](../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)」を参照してください。

```
/ASSEMBLYLINKRESOURCE:MyComponent.dll
```

## <a name="see-also"></a>関連項目

[C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)