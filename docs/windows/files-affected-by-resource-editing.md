---
title: リソースの編集によって影響を受けるファイル |Microsoft Docs
ms.custom: ''
ms.date: 06/18/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- resource editing
- resources [Visual Studio], editing
ms.assetid: d0820df1-ba84-40ac-bce9-29ea5ee7e3f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: acdf7a2915fe17cba393d14d9d287a89515695fc
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650584"
---
# <a name="files-affected-by-resource-editing"></a>リソース編集の影響を受けるファイル
Visual Studio 環境では、次の表に示すファイルがリソース編集セッション中に使用されます。  
  
|ファイル名|説明|  
|---------------|-----------------|  
|Resource.h|開発環境で生成されるヘッダー ファイル。シンボル定義が含まれます。 (このファイルはソース管理に含めます。)|  
|Filename.aps|高速読み込みに使用される、現在のリソース スクリプト ファイルのバイナリ バージョン。<br /><br /> リソース エディターは、.rc ファイルや resource.h ファイルを直接読み取りません。 リソース コンパイラがこれらのファイルをコンパイルして、リソース エディターで使用される .aps ファイルにします。 これはコンパイル手順のファイルで、シンボル データのみが格納されます。 通常のコンパイル プロセスと同様に、シンボル以外の情報 (コメントなど) はコンパイル プロセス中に破棄されます。 .aps ファイルと .rc ファイルが一致しなくなると、そのたびに .rc ファイルが再生成されます (たとえば、[保存] を実行すると、リソース エディターによって .rc ファイルと resource.h ファイルが上書きされます)。 リソース自体に対する変更は .rc ファイルに組み込まれたままですが、コメントは .rc ファイルが上書きされると失われます。 コメントを保持する方法については、次を参照してください。[コンパイル時にリソースを含む](../windows/how-to-include-resources-at-compile-time.md)します。 (通常は、含めないでください .aps ファイルでは、ソース管理。)|  
|.rc|現在のプロジェクト内のリソース用のスクリプトを格納するリソース スクリプト ファイル。 このファイルは、保存するたびに .aps ファイルで上書きされます。 (このファイルはソース管理に含めます。)|  
  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [リソース ファイル](../windows/resource-files-visual-studio.md)