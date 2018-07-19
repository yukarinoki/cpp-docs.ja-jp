---
title: '方法: ネイティブ DLL をグローバル アセンブリ キャッシュに追加 |Microsoft ドキュメント'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], native
- GAC (global assembly cache), loading native DLLs
- native DLLs [C++]
ms.assetid: 25e8d78a-b197-4269-b4e9-237a544ab3c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b7363de172eabc664bcde1e3bf42f8cc499e4251
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33129539"
---
# <a name="how-to-add-native-dll-to-global-assembly-cache"></a>方法: ネイティブ DLL をグローバル アセンブリ キャッシュに追加する
ネイティブ DLL (COM ではない) は、グローバル アセンブリ キャッシュに配置できます。  
  
## <a name="example"></a>例  
 **/ASSEMBLYLINKRESOURCE**ネイティブ DLL をアセンブリに埋め込むことができます。  
  
 詳細については、「[/ASSEMBLYLINKRESOURCE (.NET Framework リソースへのリンク)](../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)」を参照してください。  
  
```  
/ASSEMBLYLINKRESOURCE:MyComponent.dll  
```  
  
## <a name="see-also"></a>関連項目  
 [C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)