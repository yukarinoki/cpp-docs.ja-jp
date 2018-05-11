---
title: '#ifdef および #ifndef ディレクティブ (C/C++) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#ifndef'
- '#ifdef'
dev_langs:
- C++
helpviewer_keywords:
- '#ifdef directive'
- preprocessor, directives
- ifdef directive (#ifdef)
- ifndef directive (#ifndef)
- '#ifndef directive'
ms.assetid: 2b0be69d-9e72-45d8-8e24-e4130fb2455b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9a5ecfc9cc63fc4028e1f93d8f30e8d5cb9f9357
ms.sourcegitcommit: 96cdc2da0d8c3783cc2ce03bd280a5430e1ac01d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2018
---
# <a name="ifdef-and-ifndef-directives-cc"></a>#ifdef および #ifndef ディレクティブ (C/C++)
**#Ifdef**と **#ifndef**ディレクティブと同じタスクを実行する、`#if`ディレクティブと共に使用したときに**定義**( *の識別子* ).  
  
## <a name="syntax"></a>構文  
  
```  
#ifdef identifier  
#ifndef identifier  
  
// equivalent to  
#if defined identifier  
#if !defined identifier  
```  
  
## <a name="remarks"></a>コメント  
 使用することができます、 **#ifdef**と **#ifndef**ディレクティブを任意の場所`#if`使用できます。 **#Ifdef** *識別子*ステートメントは等価`#if 1`とき*識別子*を定義した後と等価であると`#if 0`とき*識別子*が定義されていないかで定義されているが、`#undef`ディレクティブです。 これらのディレクティブは、C または C++ ソース コードで宣言された識別子ではなく、`#define` で定義された識別子の有無を調べます。  
  
 これらのディレクティブは、言語の以前のバージョンとの互換性を維持するために用意されています。 **定義 (** *識別子* **)** で使用される定数式、`#if`ディレクティブをお勧めします。  
  
 **#Ifndef**ディレクティブが調べる反対の条件をチェック **#ifdef**です。 識別子を定義していない (またはその定義を `#undef` で削除した) 場合、条件は true (ゼロ以外) です。 それ以外の場合、条件は False (0) です。  
  
 **Microsoft 固有の仕様**  
  
 *識別子*/D オプションを使用してコマンドラインから渡すことができます。 最大 30 個のマクロを /D に指定できます。  
  
 定義をコマンド ラインから渡すことができるため、定義の有無を調べるために便利です。 例えば:  
  
```  
// ifdef_ifndef.CPP  
// compile with: /Dtest /c  
#ifndef test  
#define final  
#endif  
```  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)