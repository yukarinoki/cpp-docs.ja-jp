---
title: リージョン、endregion |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.endregion
- endregion_CPP
- region_CPP
- vc-pragma.region
dev_langs:
- C++
helpviewer_keywords:
- pragmas, region
- pragmas, endregion
- endregion pragma
- region pragma
ms.assetid: c697f807-622f-4796-851b-68a42bbecd84
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dac2df26f393b7491d94abdb6d987a8e424723e1
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45715560"
---
# <a name="region-endregion"></a>region、endregion
`#pragma region` 展開したり折りたたむを使用する場合のコードのブロックを指定することができます、[アウトライン機能](/visualstudio/ide/outlining)の Visual Studio コード エディター。  
  
## <a name="syntax"></a>構文  
  
```  
#pragma region name  
#pragma endregion comment  
```  
  
### <a name="parameters"></a>パラメーター  
*comment*  
(省略可能)コード エディターに表示されるコメントです。  
  
*name*  
(省略可能)領域の名前。  この名前はコード エディターに表示されます。  
  
## <a name="remarks"></a>Remarks  
 
`#pragma endregion` 末尾を`#pragma region`ブロックします。  
  
A`#region`でブロックを終了する必要があります`#pragma endregion`します。  
  
## <a name="example"></a>例  
  
```cpp  
// pragma_directives_region.cpp  
#pragma region Region_1  
void Test() {}  
void Test2() {}  
void Test3() {}  
#pragma endregion Region_1  
  
int main() {}  
```  
  
## <a name="see-also"></a>関連項目  
 
[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)