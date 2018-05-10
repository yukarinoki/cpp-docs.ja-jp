---
title: セクション |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- section_CPP
- vc-pragma.section
dev_langs:
- C++
helpviewer_keywords:
- pragmas, section
- section pragma
ms.assetid: c67215e9-2c4a-4b0f-b691-2414d2e2d96f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a8d113c10ea8370a46560ba8668546c74b19c6f8
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="section"></a>section
.obj ファイルにセクションを作成します。  
  
## <a name="syntax"></a>構文  
  
```  
  
#pragma section( "section-name" [, attributes] )  
```  
  
## <a name="remarks"></a>コメント  
 用語の意味*セグメント*と*セクション*はこのトピックでは互換性があります。  
  
 セクションを定義すると、そのセクションはそれ以降のコンパイルで有効になります。 ただし、使用する必要があります[__declspec(allocate)](../cpp/allocate.md)またはセクションに何も配置されます。  
  
 *セクション名*セクションの名前となる必須パラメーターです。 標準セクション名と競合する名前は付けられません。 参照してください[/section](../build/reference/section-specify-section-attributes.md)セクションを作成するときに使用しない名前の一覧についてはします。  
  
 省略可能なパラメーター `attributes` には、セクションに割り当てる 1 つ以上の属性をコンマで区切って指定します。 指定できる `attributes` は次のとおりです。  
  
 **read**  
 データの読み取り操作を有効にします。  
  
 **write**  
 データの書き込み操作を有効にします。  
  
 **execute**  
 コードを実行できるようにします。  
  
 **shared**  
 イメージを読み込んだすべてのプロセス間でセクションを共有します。  
  
 **nopage**  
 セクションをページング不可にします。Win32 デバイス ドライバー用です。  
  
 **nocache**  
 セクションをキャッシュ不可にします。Win32 デバイス ドライバー用です。  
  
 **discard**  
 セクションを破棄可能にします。Win32 デバイス ドライバー用です。  
  
 **remove**  
 セクションをメモリ非常駐; としてのマークを付けます仮想デバイス ドライバー (V*x*D) のみです。  
  
 属性を指定しない場合、セクションには読み取り属性と書き込み属性が設定されます。  
  
## <a name="example"></a>例  
 次の例では、最初の命令でセクションとその属性を指定しています。 `j` を使用して宣言していないので、整数 `mysec` は `__declspec(allocate)` に追加されません。`j` はデータ セクションに配置されます。 整数 `i` は、その `mysec` ストレージ クラス属性の結果として `__declspec(allocate)` に追加されます。  
  
```  
// pragma_section.cpp  
#pragma section("mysec",read,write)  
int j = 0;  
  
__declspec(allocate("mysec"))  
int i = 0;  
  
int main(){}  
```  
  
## <a name="see-also"></a>関連項目  
 [プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)