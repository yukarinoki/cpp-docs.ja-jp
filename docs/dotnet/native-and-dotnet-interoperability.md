---
title: ネイティブと .NET の相互運用性 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interop [C++]
- .NET Framework [C++], interoperability with Visual C++
- interoperability [C++], about .NET interoperability
- interop [C++], about .NET interoperability
- managed code [C++], interoperability
- native code [C++]
- interoperability [C++]
- MFC [C++], .NET integration
- unmanaged code interoperability [C++]
- Visual C++, interoperability
- native code [C++], .NET interoperatibility
ms.assetid: f3ec6c99-c745-4256-b95b-f1d12ba17a5a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: cabd21f400b7c0c21faefdf2004dee9ae2cc64ac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="native-and-net-interoperability"></a>ネイティブと .NET の相互運用性
Visual C++ では相互運用機能をサポートしており、マネージ構造とアンマネージ構造が共存して同じアセンブリ内ではもちろん、同じファイル内でも相互運用できます。 この機能の小さなサブセット (P/Invoke など) は他の .NET 言語でもサポートされていますが、Visual C++ が提供する相互運用性サポートのほとんどは他の言語では使用できません。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [混在 (ネイティブおよびマネージ) アセンブリ](../dotnet/mixed-native-and-managed-assemblies.md)  
 使用して生成されたアセンブリについて説明します、 [/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)両方を含むコンパイラ オプションがマネージし、アンマネージ機能します。  
  
 [MFC での Windows フォーム ユーザー コントロールの使用](../dotnet/using-a-windows-form-user-control-in-mfc.md)  
 MFC Windows フォーム サポート クラスを使用して MFC アプリケーション内で Windows フォーム コントロールをホストする方法について説明します。  
  
 [マネージ コードからのネイティブ関数の呼び出し](../dotnet/calling-native-functions-from-managed-code.md)  
 非 CLR DLL を .NET アプリケーションから使用する方法について説明します。  
  
## <a name="see-also"></a>関連項目  


