<template>
  <div>
    <div>
      <h2 class="text-2xl font-medium">나의 문의</h2>
      <p>문의를 입력해 주시면 담당자가 확인 후 연락 드리겠습니다.</p>
    </div>

    <div class="mt-10">
      <div>
        <strong>문의구분</strong>
        <Select>
          <SelectTrigger>
            <SelectValue placeholder="선택" />
          </SelectTrigger>
          <SelectContent>
            <SelectGroup>
              <SelectItem value="opt1"> OPT1 </SelectItem>
              <SelectItem value="opt2"> OPT2 </SelectItem>
            </SelectGroup>
          </SelectContent>
        </Select>
      </div>
      <div>
        <strong>소속명</strong>
        <Input />
      </div>
      <div>
        <strong>이름</strong>
        <Input />
      </div>
      <div>
        <strong>연락처</strong>
        <div class="flex items-center">
          <Input />
          <p>-</p>
          <Input />
          <p>-</p>
          <Input />
        </div>
      </div>
      <div>
        <strong>이메일</strong>
        <Input />
      </div>
      <div>
        <strong>문의내용</strong>
        <Textarea placeholder="내용 입력" />
      </div>
    </div>
    <Button>문의하기</Button>
  </div>
</template>

<script setup lang="ts"></script>

<style scoped></style>
