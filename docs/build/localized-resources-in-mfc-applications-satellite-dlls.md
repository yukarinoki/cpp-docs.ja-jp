---
title: MFC アプリケーションのローカライズされたリソース:サテライト DLL
ms.date: 11/04/2016
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
ms.openlocfilehash: 1f512cc17832564b5eb530b97f8bfb2642c43d43
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220744"
---
# <a name="localized-resources-in-mfc-applications-satellite-dlls"></a>MFC アプリケーションのローカライズされたリソース:サテライト DLL

MFC バージョン 7.0 以降ではサテライト DLL のサポートが強化されています。これは、混合言語にローカライズされるアプリケーションの作成に役立つ機能です。 サテライト DLL は、特定の言語にローカライズされたアプリケーションのリソースを含む[リソースのみの DLL](creating-a-resource-only-dll.md) です。 アプリケーションの実行が開始されると、環境に最適なローカライズされたリソースが MFC によって自動的に読み込まれます。 たとえば、リソースのフランス語翻訳とドイツ語翻訳を含む 2 つのサテライト DLL を備えた英語リソースを持つアプリケーションがあるとします。 アプリケーションが英語のシステム上で実行されると、英語のリソースが使用されます。 フランス語のシステム上で実行されると、フランス語のリソースが使用されます。ドイツ語のシステム上で実行されると、ドイツ語のリソースが使用されます。

MFC アプリケーションでローカライズされたリソースをサポートするために、MFC では特定の言語にローカライズされたリソースを含むサテライト DLL の読み込みが試行されます。 サテライト DLL の名前は *ApplicationNameXXX*.dll です。この *ApplicationName* は MFC を使用する .exe または .dll の名前であり、*XXX* はリソースの言語を表す 3 文字のコードで (たとえば、'ENU'、'DEU')。

MFC では、次の各言語のリソース DLL の読み込みが順番に試行され、見つかると停止されます。

1. GetUserDefaultUILanguage() Win32 API から返される現在のユーザーの既定の UI 言語。

1. 特定のサブ言語を含まない現在のユーザーの既定の UI 言語 (つまり、ENC [Canadian English] は ENU [U.S. English] になります)。

1. GetSystemDefaultUILanguage() API から返されるシステムの既定の UI 言語。 他のプラットフォームでは、これは OS 自体の言語です。

1. 特定のサブ言語のない、システムの既定の UI 言語。

1. 3 文字のコード LOC を使用した偽の言語。

MFC でサテライト DLL が検出されない場合は、アプリケーション自体に含まれているリソースが何であろうとそれが使用されます。

たとえば、アプリケーション LangExample.exe で MFC が使用され、複数のユーザーインターフェイス システムで実行されているとします。このシステムの UI 言語は ENU [U.S. English] であり、現在のユーザーの UI 言語は FRC [Canadian French] に設定されています。 MFC では、次の DLL が次の順序で検索されます。

1. LangExampleFRC.dll (ユーザーの UI 言語)。

1. LangExampleFRA.dll (サブ言語なしのユーザーの UI 言語、この例では French (France))。

1. LangExampleENU.dll (システムの UI 言語)。

1. LangExampleLOC.dll。

これらの DLL が見つからない場合、MFC では LangExample.exe のリソースが使用されます。

## <a name="see-also"></a>関連項目

[Visual Studio での C/C++ Dll の作成](dlls-in-visual-cpp.md)<br/>
[テクニカル ノート 57: MFC コンポーネントのローカライズ](../mfc/tn057-localization-of-mfc-components.md)
