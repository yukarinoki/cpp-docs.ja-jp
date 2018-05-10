---
title: 'MFC アプリケーションのローカライズされたリソース: サテライト Dll |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- multiple language support [C++]
- localization [C++], MFC resources
- localized resources [C++]
- MFC DLLs [C++], localizing
- DLLs [C++], localizing MFC
- resources [MFC], localizing
- resource-only DLLs [C++]
- resource-only DLLs [C++], MFC applications
- satellite DLLs [C++]
ms.assetid: 3a1100ae-a9c8-47b5-adbd-cbedef5992ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0740f567f17c8d44069211274ab1a4c66da311c1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="localized-resources-in-mfc-applications-satellite-dlls"></a>MFC アプリケーションのローカライズされたリソース: サテライト DLL
MFC version 7.0 以降では、サテライト Dll の場合、複数の言語にローカライズされるアプリケーションを作成するときに役立つ機能のサポートの強化を提供します。 DLL は、サテライト、[リソース専用 DLL](../build/creating-a-resource-only-dll.md)特定の言語のローカライズされたアプリケーションのリソースを格納しています。 アプリケーションでは、実行を開始、MFC は自動的に、環境に最適なローカライズされたリソースを読み込みます。 たとえば、2 つのサテライト Dll、リソースとドイツ語の翻訳を含むその他のフランス語翻訳が含まれていると英語の言語リソースを持つアプリケーションことができます。 英語のシステムでは、アプリケーションが実行されるときに、英語のリソースを使用します。 フランス語のリソースを使用して、フランス語のシステムで実行される場合ドイツ語のシステムで実行される場合は、ドイツ語のリソースを使用します。  
  
 MFC アプリケーション、サテライト DLL をロードしようと MFC のローカライズされたリソースをサポートするためにリソースを含む、特定の言語にローカライズされます。 サテライト Dll の名前は*ApplicationNameXXX*.dll、場所*ApplicationName*の .exe または .dll、MFC を使用して名前を指定し、 *XXX*言語に対する 3 文字コードは、リソース (たとえば、'日本語' または 'DEU')。  
  
 MFC では、1 つを見つけたときに停止する順序で次の言語の各リソース DLL をロードしようとしています。  
  
1. 現在のユーザーの既定の UI 言語、GetUserDefaultUILanguage() Win32 API から返されます。  
  
2.  サブ言語が指定せず、現在のユーザーの既定の UI 言語 (つまり、ENC [カナダ英語] になる日本語 [米国英語])。  
  
3.  システムの既定の UI 言語、GetSystemDefaultUILanguage() API から返されます。 その他のプラットフォームでは、これは OS の言語です。  
  
4.  システムの既定の UI 言語、サブ言語が指定なし。  
  
5.  3 文字コード LOC を持つ偽言語  
  
 サテライト Dll が見つからない場合は、MFC、アプリケーション自体に含まれるすべてのリソースが使用されます。  
  
 たとえば、アプリケーション LangExample.exe が MFC を使用し、複数のユーザー インターフェイス システム; で実行されているとしますシステム UI 言語が英語 [米国です。英語] 現在のユーザーの UI 言語が FRC [カナダ フランス語] に設定されているとします。 MFC は、次の順序で次の Dll を探します。  
  
1.  LangExampleFRC.dll (ユーザーの UI 言語)。  
  
2.  LangExampleFRA.dll (フランス語 (フランス) この例では、サブ言語なしのユーザーの UI 言語。  
  
3.  LangExampleENU.dll (システムの UI 言語)。  
  
4.  LangExampleLOC.dll.  
  
 これらの Dll が見つからない場合、MFC は LangExample.exe でリソースを使用します。  
  
## <a name="see-also"></a>関連項目  
 [Visual C の Dll](../build/dlls-in-visual-cpp.md)   
 [テクニカル ノート 57: MFC コンポーネントのローカライズ](../mfc/tn057-localization-of-mfc-components.md)