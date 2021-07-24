---
title: 'Introduction to Blockchain'
date: 'May 5, 2021'
excerpt: 'Blockchains are cool'
cover_image: '/images/posts/img3.jpg'
category: 'Python'
author: 'Sam Smith'
author_image: 'https://randomuser.me/api/portraits/men/12.jpg'
---
# 블록체인 소개

# **블록체인**이란?

**블록체인**이란 데이터를 나누어 저장하는 데이터 분산 처리 기술입니다.

데이터를 특정 `블록`으로 나누고 이 블록들을 차례로 연결되어 사슬 구조를 가지게 되는 것이죠.

한 네트워크 상의 모든 사용자가 이 블록의 사슬, 즉 블록체인을 가지고 있으므로 특정 데이터를 위조하거나 조작하는 것이 거의 불가능합니다.

(이 네트워크의 대표적 예로 비트코인과 같은 암호 화폐가 있습니다. 비트코인 채굴자와 소비자들 모두 `비트코인 네트워크`에 연결된 것입니다.)

## 왜 등장했나?

블록체인은 한마디로 정의하면 `장부`입니다.

즉, 금융거래에 사용되기 위해 만들어졌다고 보면 되는데, 그럼 왜 현재의 거래 방식과 다른 방법을 만들었을까요?

그 이유는 **중앙화**때문입니다.

현재 금융거래는 은행과 같은 중앙 기관에서 모든 거래 내역을 관리합니다.

문제는 이 경우 중앙 기관이 해킹당하거나 실수로 인해 거래 내역이 실제와 달라지면 해당 기관을 사용하는 모든 곳에서 문제가 일어날 수 있다는 것입니다.

또한, 사용자는 중앙 기관이 어떤 일을 내부적으로 하는지 알 수 없고 보안 문제를 해결하기 위해 제삼자가 들어오면 거래 시간이 늘어나고 전체적으로 일이 많아지죠.

이런 문제를 해결하기 위해 블록체인은 `탈중앙화`를 선언합니다.

중앙 기관 없이 사용자들이 직접 장부를 가지고 있으니 공개적이고 사용자들이 직접 암호화하니 제삼자의 개입 없이 비교적 빠르게 거래가 일어날 수 있게 되죠.

***요점: 블록체인은 중앙화된 현재의 거래방식보다 더 빠르고 공개적이며 더 안전하다.***

## 어떻게 작동하는가?

블록체인 네트워크의 각 사용자는 `노드`라고 불리며 각 노드는 장부의 전체 혹은 일부를 가진다.

*아래 설명은 비트코인을 예로 설명합니다.*

어떤 거래가 발생하면 이 거래가 정당한 거래인지 노드들이 합의하는데, 일종의 투표라고 생각하면 된다.

이때, 1표의 가치가 모두 같은 대한민국의 투표 원칙과 다르게, `작업 증명`이라는 작업을 가장 많이 한 노드의 투표권이 더 큰 힘을 가지게 된다.

### 작업 증명

작업 증명은 컴퓨터 연산을 통해 처리되는데 그 과정은 다음과 같다.

1. 거래 내용을 숫자(16진수)로 바꾼다.
2. 블록이 자동으로 특정 `난이도`(혹은 기준)를 설정하며 노드는 0부터 1씩 증가하며 특정 계산을 합니다.
3. 계산된 결과가 이 난이도보다 낮으면서 거래 내용을 숫자로 바꾼 것과 연관이 있다면 작업을 증명했다고 봅니다.
4. 작업 증명이 완료되면 거래가 블록에 기록되어 작업 증명을 완료한 노드의 장부에 기록되며 추후 다른 컴퓨터에도 이 블록이 기록됩니다.

이 작업 증명의 과정은 단순히 수식을 계산하면 되기 때문에 한 번에 다양한 연산을 하여 최대한 빨리 많은 양의 수에 대해 계산을 하는 것이 효율적입니다.

이로 인해 코어 수가 많으면서 상대적으로 가격이 싼 그래픽 카드를 암호 화폐 채굴에 사용하게 되죠. (CPU는 코어가 많아야 몇십 개지만 그래픽 카드는 수천 개의 코어를 가집니다.)

암호 화폐와 관련하여 그래픽 카드 가격이 높아지는 것은 이러한 이유로 인한 것이라고 볼 수 있습니다.

## 왜 안전한가?

이제 블록체인이 작동하는 방식이 어느 정도 감이 왔을 것으로 생각합니다.

그런데 왜 안전한지는 아직 이유가 부족하다고 느낄 수 있습니다.

특히, 작업 증명을 완료하면 완료한 노드의 장부에 먼저 기록되고 다른 노드에 기록되기에 그사이에 해킹하면 되는 것이 아닌지, 아니면 애초에 그냥 해킹하면 되는 것 아닌지 의문이 있을 수 있습니다.

우선, 작업 증명은 수많은 노드가 하나의 거래에 대해 작업 증명을 실시합니다.

이 수많은 노드 중 어떤 노드가 먼저 증명을 마치면 나머지 노드들은 그 즉시 증명된 값을 가진 블록이 장부에 기록되기 때문에 기본적으로 한 장부만 어떤 거래 내역을 가지는 경우는 거의 없으며 있더라고 매우 짧은 한순간일 뿐입니다.

해커가 블록체인을 해킹하는 방법은 (1) **모든 장부의 모든 거래 내역을 바꾸거나**, (2) **작업 증명을 마친 노드가 그 정보를 네트워크로 보내지 전에 바꾸거나**, (3) **작업 증명이 마치기 전에 원하는 정보를 네트워크에 보내는 것** 외엔 없습니다.

(1) 현실적으로 네트워크가 매우 작지 않은 이상 모든 장부를 바꾸는 것을 불가능합니다. 또한, (2) 작업 증명을 하는 노드는 굉장히 많고 익명성을 가지기에 해커가 어떤 노드가 작업 증명을 마쳤는지 알 수 없습니다. 마지막으로, (3) 작업 증명이 끝나기 전에 정보를 보내려면 실존하는 가장 빠른 슈퍼컴퓨터의 성능을 넘어서는 연산력이 요구되기에 불가능하다고 볼 수 있습니다.

여기서 (3)이 하는 일은 전에 노드들의 합의를 통해 거래를 정당화한다고 했는데, 만약 어떤 거래에 대해 이미 장부에 기록되어 있는 내역이 있다면 실제 작업 증명을 마친 값이 무시될 수 있기에 가능합니다.

(그러나 요즘 대두하고 있는 양자컴퓨터는 (3)의 문제를 현실화할 수 있어 우려의 목소리도 나오는 추세입니다.)

## 블록체인이 사용되는 곳

블록체인은 비트코인과 같은 암호 화폐로 유명하지만, 그 개념과 연관 기술들은 보안과 관련된 분야 하면 전부 사용될 수 있는 특징을 지닙니다.

은행과 같은 금융기관이나 보안 서비스(로그인과 같은 서비스)에서 사용될 수 있습니다.

실제로 미국의 몇몇 주에서는 블록체인을 투표시스템으로 사용할 계획 중에 있다고 합니다.

## 블록체인 개념 공부 후 든 생각

원래 블록체인이 무엇인지 간단하게는 알고 있었지만, 자세히 공부해보니 복잡한 문제를 해결하기 위해 굉장히 단순한 방법을 사용했다는 것을 깨달았고 이런 방식을 생각해냈다는 것이 놀라웠다.

또한, 블록체인에 대해 알고 나니 암호 화폐나 블록체인을 이용한 서비스를 만들어보고 싶어 졌다.

다만, 양자컴퓨터의 발달이 현재 개발되고 있는 여러 보안 기술들을 타파할 수 있다니 그에 따른 대비책 등은 어떤 것이 있는지 더 알아보고 싶다.

### 타입스크립트로 구현한 간단한 블록체인

출처: [https://github.com/nomadcoders/typechain](https://github.com/nomadcoders/typechain)

```tsx
import * as CryptoJS from "crypto-js"; //블록의 값을 계산하기 위해 사용

class Block {
  static calculateBlockHash = (
    index: number,
    previousHash: string,
    timestamp: number,
    data: string
  ): string =>
    CryptoJS.SHA256(index + previousHash + timestamp + data).toString();
    // 블록의 값을 계산하는 함수

  static validateStructure = (aBlock: Block): boolean =>
    typeof aBlock.index === "number" &&
    typeof aBlock.hash === "string" &&
    typeof aBlock.previousHash === "string" &&
    typeof aBlock.timestamp === "number" &&
    typeof aBlock.data === "string";
    // 블록의 형태가 정당한 형태인지 확인
  public index: number;
  public hash: string;
  public previousHash: string;
  public data: string;
  public timestamp: number;

  constructor(
    index: number,
    hash: string,
    previousHash: string,
    data: string,
    timestamp: number
  ) {
    this.index = index;
    this.hash = hash;
    this.previousHash = previousHash;
    this.data = data;
    this.timestamp = timestamp;
  } // 블록 생성
}

const genesisBlock: Block = new Block(0, "2020202020202", "", "Hello", 123456);
//최초의 블록 생성
let blockchain: Block[] = [genesisBlock];
// 블록의 체인을 저장 = 장부
const getBlockchain = (): Block[] => blockchain;
// 블록체인 장부를 가져오는 함수
const getLatestBlock = (): Block => blockchain[blockchain.length - 1];
// 가장 최신 블록
const getNewTimeStamp = (): number => Math.round(new Date().getTime() / 1000);
// 현재 시간을 숫자로 변환 ( 1970년 1월 1일부터 지금까지의 시간을 1/1000초 기준으로 차를 구함)
const createNewBlock = (data: string): Block => {
  const previousBlock: Block = getLatestBlock();
  const newIndex: number = previousBlock.index + 1;
  const newTimestamp: number = getNewTimeStamp();
  const newHash: string = Block.calculateBlockHash(
    newIndex,
    previousBlock.hash,
    newTimestamp,
    data
  );
  const newBlock: Block = new Block(
    newIndex,
    newHash,
    previousBlock.hash,
    data,
    newTimestamp
  );
  addBlock(newBlock); //.....(1)
  return newBlock;
}; // 새로운 블록을 만들고 장부에 추가(아직 완전히 추가되지 않음 - (1)의 실행결과에 따라 달라짐)

const getHashforBlock = (aBlock: Block): string =>
  Block.calculateBlockHash(
    aBlock.index,
    aBlock.previousHash,
    aBlock.timestamp,
    aBlock.data
  ); // 블록의 내용을 숫자로 바꿈 (작업 증명의 1번)

const isBlockValid = (candidateBlock: Block, previousBlock: Block): boolean => {
  if (!Block.validateStructure(candidateBlock)) {
    return false;
  } else if (previousBlock.index + 1 !== candidateBlock.index) {
    return false;
  } else if (previousBlock.hash !== candidateBlock.previousHash) {
    return false;
  } else if (getHashforBlock(candidateBlock) !== candidateBlock.hash) {
    return false;
  } else {
    return true;
  }
}; // 블록이 장부에 들어가는 것이 정당한지 확인 - 형태, 위치, 숫자(난이도)

const addBlock = (candidateBlock: Block): void => {
  if (isBlockValid(candidateBlock, getLatestBlock())) {
    blockchain.push(candidateBlock);
  }
}; // 블록이 들어갈 수 있는지 확인 후 장부에 기입

createNewBlock("second block");
createNewBlock("third block");
createNewBlock("fourth block");
// 테스트용 블록 생성 및 추가
console.log(blockchain);
// 장부 출력
export {};

```

### 출처

[https://www.youtube.com/watch?v=9V1bipPkCTU](https://www.youtube.com/watch?v=9V1bipPkCTU)

[https://ko.wikipedia.org/wiki/작업\\_증명\\_시스템](https://ko.wikipedia.org/wiki/%EC%9E%91%EC%97%85%5C%5C_%EC%A6%9D%EB%AA%85%5C%5C_%EC%8B%9C%EC%8A%A4%ED%85%9C)

[https://www.ibm.com/kr-ko/topics/what-is-blockchain](https://www.ibm.com/kr-ko/topics/what-is-blockchain)

[https://ko.wikipedia.org/wiki/블록체인](https://ko.wikipedia.org/wiki/%EB%B8%94%EB%A1%9D%EC%B2%B4%EC%9D%B8)

[https://www.banksalad.com/contents/쉽게-설명하는-블록체인-블록체인의-원리-채굴-해시-그리고-작업증명-qvCud](https://www.banksalad.com/contents/%EC%89%BD%EA%B2%8C-%EC%84%A4%EB%AA%85%ED%95%98%EB%8A%94-%EB%B8%94%EB%A1%9D%EC%B2%B4%EC%9D%B8-%EB%B8%94%EB%A1%9D%EC%B2%B4%EC%9D%B8%EC%9D%98-%EC%9B%90%EB%A6%AC-%EC%B1%84%EA%B5%B4-%ED%95%B4%EC%8B%9C-%EA%B7%B8%EB%A6%AC%EA%B3%A0-%EC%9E%91%EC%97%85%EC%A6%9D%EB%AA%85-qvCud)

[https://www.banksalad.com/contents/쉽게-설명하는-블록체인-비트코인-거래가-이루어지는-과정-L7bWb](https://www.banksalad.com/contents/%EC%89%BD%EA%B2%8C-%EC%84%A4%EB%AA%85%ED%95%98%EB%8A%94-%EB%B8%94%EB%A1%9D%EC%B2%B4%EC%9D%B8-%EB%B9%84%ED%8A%B8%EC%BD%94%EC%9D%B8-%EA%B1%B0%EB%9E%98%EA%B0%80-%EC%9D%B4%EB%A3%A8%EC%96%B4%EC%A7%80%EB%8A%94-%EA%B3%BC%EC%A0%95-L7bWb)

[https://www.banksalad.com/contents/블록체인-개념-완벽-정리-dh1do](https://www.banksalad.com/contents/%EB%B8%94%EB%A1%9D%EC%B2%B4%EC%9D%B8-%EA%B0%9C%EB%85%90-%EC%99%84%EB%B2%BD-%EC%A0%95%EB%A6%AC-dh1do)

[https://www.banksalad.com/contents/쉽게-이해하는-블록체인-비트코인-블록체인이란-무엇인가-0vLh5](https://www.banksalad.com/contents/%EC%89%BD%EA%B2%8C-%EC%9D%B4%ED%95%B4%ED%95%98%EB%8A%94-%EB%B8%94%EB%A1%9D%EC%B2%B4%EC%9D%B8-%EB%B9%84%ED%8A%B8%EC%BD%94%EC%9D%B8-%EB%B8%94%EB%A1%9D%EC%B2%B4%EC%9D%B8%EC%9D%B4%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80-0vLh5)