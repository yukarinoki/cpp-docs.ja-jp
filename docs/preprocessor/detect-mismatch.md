---
title: detect_mismatch |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.detect_mismatch
- detect_mismatch_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, detect_mismatch
- detect_mismatch pragma
ms.assetid: ddb13ac9-0e2f-40ce-be69-7e44c04f5a12
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9f30afed5acdb9da433f7ce5f992df9bcb6dc8f5
ms.sourcegitcommit: 96cdc2da0d8c3783cc2ce03bd280a5430e1ac01d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2018
---
# <a name="detectmismatch"></a>detect_mismatch
オブジェクト内にレコードを配置します。 リンカーは、不一致の可能性を探してこれらのレコードをチェックします。  
  
## <a name="syntax"></a>構文  
  
```  
#pragma detect_mismatch( "name", "value"))  
```  
  
## <a name="remarks"></a>コメント  
 プロジェクトのリンク時に、同じ `LNK2038` を持つが `name` がそれぞれ異なる 2 つのオブジェクトがプロジェクトに含まれている場合、リンカーは `value` エラーをスローします。 整合性のないオブジェクト ファイルのリンクを防止するには、このプラグマを使用します。  
  
 名前と値の両方が文字列リテラルで、エスケープ文字と連結に関して文字列リテラルの規則に準拠します。 これらは大文字と小文字を区別し、コンマ、等号、引用符、または `null` 文字を含めることはできません。  
  
## <a name="example"></a>例  
 この例では、同じバージョン ラベルの異なるバージョン番号を持つ 2 つのファイルを作成します。  
  
```  
// pragma_directive_detect_mismatch_a.cpp  
#pragma detect_mismatch("myLib_version", "9")  
int main ()  
{  
   return 0;  
}  
  
// pragma_directive_detect_mismatch_b.cpp  
#pragma detect_mismatch("myLib_version", "1")  
```  
  
 コマンド ライン `cl pragma_directive_detect_mismatch_a.cpp pragma_directive_detect_mismatch_b.cpp` を使用してこれらの両方のファイルをコンパイルすると、エラー `LNK2038` が表示されます。  
  
## <a name="see-also"></a>関連項目  
 [プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)