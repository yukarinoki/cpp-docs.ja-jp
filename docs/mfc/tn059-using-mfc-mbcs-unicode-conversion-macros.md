---
title: 'TN059: MFC の MBCS Unicode 変換マクロの使用 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.mbcs
dev_langs:
- C++
helpviewer_keywords:
- MFCANS32.DLL
- Unicode [MFC], conversion macros
- Unicode [MFC], OLE interfaces
- conversion macros [MFC]
- converting Unicode
- MBCS [MFC], conversion macros
- macros [MFC], MBCS conversion macros
- TN059
ms.assetid: a2aab748-94d0-4e2f-8447-3bd07112a705
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 379c5b4fb9ed302ad1ea0167f2b32c30e48ab2bf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="tn059-using-mfc-mbcsunicode-conversion-macros"></a>テクニカル ノート 59: MFC の MBCS/Unicode 変換マクロの使用
> [!NOTE]
>  次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。  
  
 ここでは、AFXPRIV で定義されている Mbcs/unicode 変換マクロを使用する方法について説明します。H. これらのマクロはアプリケーション商談直接 OLE API でまたは何らかの理由により、多くの場合、必要がある Unicode と MBCS の間で変換する場合に特に役立ちます。  
  
## <a name="overview"></a>概要  
 Mfc 3.x、特別な DLL が (MFCANS32 を使用します。DLL) をクリックし、OLE インターフェイスが呼び出されたときに、Unicode と MBCS の間で自動的に変換します。 この DLL が OLE アプリケーションを書き込む場合と同様、OLE Api とインターフェイス MBCS、であっても、常に Unicode を許可されているほぼ透過的なレイヤー (Macintosh 上を除く)。 この層が便利なときに、簡単に移植して Win16 から Win32 にアプリケーションを許可 (MFC、Microsoft Word、Excel、および VBA ではこのテクノロジを使用した Microsoft アプリケーションの一部)、大幅なパフォーマンスがヒットします。 このため、MFC 4.x がこの DLL を使用しないと、代わりに Unicode OLE インターフェイスに直接通信します。 これを行うには、MFC は、OLE インターフェイスへの呼び出しを行うときに、MBCS に Unicode に変換する必要があり、多くの場合、OLE インターフェイスを実装する場合は、Unicode から MBCS に変換する必要があります。 この処理を行う簡単かつ効率的にするためにいくつかのマクロはこの変換を容易に作成されました。  
  
 このような一連のマクロを作成する最も大きな難関の 1 つは、メモリの割り当てです。 インプレース文字列に変換できないために、変換した結果を格納する新しいメモリを割り当てる必要があります。 これは、可能性がありますが完了すると、次のようなコード。  
  
```  
// we want to convert an MBCS string in lpszA  
int nLen = MultiByteToWideChar(CP_ACP,
    0,
    lpszA, -1,
    NULL,
    NULL);

LPWSTR lpszW = new WCHAR[nLen];  
MultiByteToWideChar(CP_ACP,
    0,   
    lpszA, -1,
    lpszW,
    nLen);

// use it to call OLE here  
pI->SomeFunctionThatNeedsUnicode(lpszW);

// free the string  
delete[] lpszW;  
```  
  
 この方法には、さまざまな問題ではします。 主な問題は、多くの記述、テスト、およびデバッグするコードであることです。 単純な関数が呼び出されました、はるかに複雑になっているものです。 さらに、これにオーバーヘッドが大幅なランタイムがあります。 メモリにするため、ヒープに割り当てられた変換が行われるたびを解放します。 最後に、上記のコードが必要に適切な`#ifdefs`(これを行うには、この変換を必要としない) ビルドの Unicode および Macintosh 追加します。  
  
 思いつきましたソリューションでは、いくつかのマクロをどのマスク 1) との差分、さまざまなプラットフォームでは、2) を使用して、効率的なメモリの割り当て方法および 3) は、既存に簡単に挿入のソース コードを作成します。 いずれかの定義の例を次に示します。  
  
```  
#define A2W(lpa) (\  
 ((LPCSTR)lpa == NULL) NULL : (\  
    _convert = (strnlen(lpa)+1),\  
    AfxA2WHelper((LPWSTR) alloca(_convert*2),   
    lpa,
    _convert)\)\)  
```  
  
 この上記のコードではなくマクロと処理を使用したは、はるかに簡単です。  
  
```  
// use it to call OLE here  
USES_CONVERSION;  
pI->SomeFunctionThatNeedsUnicode(T2OLE(lpszA));
```  
  
 ここで変換が必要に応じてがマクロを使用する簡単で効果的な余分な呼び出しがあります。  
  
 各マクロの実装では、ヒープではなく、スタックからメモリを割り当てる _alloca() 関数を使用します。 スタックからのメモリの割り当ては、ヒープのメモリを割り当てる場合よりもはるかに高速とメモリは、関数が終了したときに自動的に解放します。 マクロが通話を回避するさらに、 **MultiByteToWideChar** (または**WideCharToMultiByte**) 1 つ以上の時間。 これは、必要なは、もう少し以上のメモリを割り当てることによって行います。 MBC は多くても 1 つに変換されていることが分かって**WCHAR**と各**WCHAR**が 2 文字の最大数。 必ずがよりは少し多く必要に応じて、割り当てることによって変換を処理する、2 番目の呼び出し 2 番目の変換関数の呼び出しを回避できます。 ヘルパー関数を呼び出す**AfxA2Whelper**が変換を実行するために行う必要がある引数のプッシュの数が減り、(この結果より小さなコードよりも呼び出される場合**MultiByteToWideChar**直接)。  
  
 領域がないマクロを格納する順に、変換マクロを使用するは、各関数でを変換 (_c) と呼ばれるローカル変数を宣言する必要がある一時的な長さです。 呼び出すことによってこれは、 **USES_CONVERSION**マクロの例では、上で説明します。  
  
 汎用変換マクロと OLE 固有のマクロの両方があります。 これら 2 つの異なるマクロ セットを次に説明します。 すべてのマクロは、AFXPRIV に存在します。H.  
  
## <a name="generic-conversion-macros"></a>汎用変換マクロ  
 汎用変換マクロは、基になるメカニズムを形成します。 マクロの例と A2W、前のセクションで示すように実装は、このような 1 つの「汎用」マクロです。 OLE を具体的には関係ことはありません。 ジェネリックのマクロのセットは次のとおりです。  
  
```  
A2CW      (LPCSTR) -> (LPCWSTR)  
A2W      (LPCSTR) -> (LPWSTR)  
W2CA      (LPCWSTR) -> (LPCSTR)  
W2A      (LPCWSTR) -> (LPSTR)  
```  
  
 テキスト変換を行うだけでなくもマクロとを変換するためのヘルパー関数`TEXTMETRIC`、 `DEVMODE`、 `BSTR`、および OLE 文字列が割り当てられます。 これらのマクロはここでは扱いません - AFXPRIV を参照してください。詳細については、これらのマクロ H します。  
  
## <a name="ole-conversion-macros"></a>OLE 変換マクロ  
 OLE 変換マクロが期待する関数の処理用に設計された**OLESTR**文字です。 OLE ヘッダーを確認する場合に多くの参照が表示されます**LPCOLESTR**と**OLECHAR**です。 これらの型は、プラットフォームに固有ではない方法での OLE インターフェイスで使用される文字の種類を参照に使用されます。 **OLECHAR**にマップ`char`Win16 または Macintosh プラットフォームと**WCHAR** Win32 でします。  
  
 数を保持するために **#ifdef** MFC でのディレクティブのコードを最小限に抑えるの各変換のようなマクロがあることを OLE 文字列が関係しています。 次のマクロがよく使用されます。  
  
```  
T2COLE   (LPCTSTR) -> (LPCOLESTR)  
T2OLE   (LPCTSTR) -> (LPOLESTR)  
OLE2CT   (LPCOLESTR) -> (LPCTSTR)  
OLE2T   (LPCOLESTR) -> (LPCSTR)  
```  
  
 ここでも、そのようなマクロがあります`TEXTMETRIC`、 `DEVMODE`、 `BSTR`、および OLE 文字列が割り当てられます。 AFXPRIV を参照してください。詳細については H します。  
  
## <a name="other-considerations"></a>その他の注意事項  
 ループの中でマクロを使用しないでください。 たとえば、次のようなコードを記述することはおたくないです。  
  
```  
void BadIterateCode(LPCTSTR lpsz)  
{  
    USES_CONVERSION; 
    for (int ii = 0; ii <10000; ii++)  
    pI->SomeMethod(ii, T2COLE(lpsz));

}  
```  
  
 上記のコードがどのような文字列の内容によってスタックにメモリのメガバイト数を割り当て、可能性があります`lpsz`は! ループの各イテレーションの文字列に変換する時間もかかります。 代わりに、このような定数の変換はループの外に移動します。  
  
```  
void MuchBetterIterateCode(LPCTSTR lpsz)  
{  
    USES_CONVERSION; 
    LPCOLESTR lpszT = T2COLE(lpsz);

    for (int ii = 0; ii <10000; ii++)  
    pI->SomeMethod(ii, lpszT);

}  
```  
  
 文字列が定数でない場合は、関数にメソッドの呼び出しをカプセル化します。 これは、毎回解放する変換バッファーで許可されます。 例えば:  
  
```  
void CallSomeMethod(int ii, LPCTSTR lpsz)  
{  
    USES_CONVERSION; 
    pI->SomeMethod(ii, T2COLE(lpsz));

}  
 
void MuchBetterIterateCode2(LPCTSTR* lpszArray)  
{  
    for (int ii = 0; ii <10000; ii++)  
    CallSomeMethod(ii, lpszArray[ii]);

}  
```  
  
 戻り値は、戻り値の前にデータのコピーを作成することを意味しない限り、マクロのいずれかの結果を返すことはありません。 たとえば、このコードは正しくありません。  
  
```  
LPTSTR BadConvert(ISomeInterface* pI)  
{  
    USES_CONVERSION; 
    LPOLESTR lpsz = NULL;  
    pI->GetFileName(&lpsz);

 LPTSTR lpszT = OLE2T(lpsz);

    CoMemFree(lpsz);

 return lpszT; // bad! returning alloca memory  
}  
```  
  
 上記のコードは、値がコピーされるように、戻り値を変更することで修復可能性があります。  
  
```  
CString BetterConvert(ISomeInterface* pI)  
{  
    USES_CONVERSION; 
    LPOLESTR lpsz = NULL;  
    pI->GetFileName(&lpsz);

 LPTSTR lpszT = OLE2T(lpsz);

    CoMemFree(lpsz);

 return lpszT; // CString makes copy  
}  
```  
  
 マクロは使いやすく、簡単に、コードに挿入しますが、上の注意事項がありますから分かるようには、これらを使用する際は注意する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)

