# trucks-on-bridge
#python
bridge_length,weight,truck_weights 값이 각각 주어집니다. 다리에는 트럭이 최대 bridge_length대 올라갈 수 있으며, 다리는 weight 이하까지의 무게를 견딜 수 있습니다. 단, 다리에 완전히 오르지 않은 트럭의 무게는 무시합니다. 모든 트럭이 다리를 건너려면 최소 몇 초가 걸리는 지를 구하는 프로그램을 작성해보자!

def solution(bridge_length, weight, truck_weights):
    answer = 0
    bridge=[0]*bridge_length
    while len(bridge):
        answer+=1
        bridge.pop(0)
        if truck_weights:
            if (sum(bridge)+truck_weights[0])<=weight:  bridge.append(truck_weights.pop(0)) #첫번째 항목값을 bridge에 추가
            else:  bridge.append(0)
    return answer
bridge_length=2
weight=10
truck_weights=[7,4,5,6]
a=solution(bridge_length, weight, truck_weights)
print(a)

결과-> 8(초)
