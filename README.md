class Scanner:
    def __init__(self, input_stream):
        self._input_stream = input_stream

    def scan(self):
        # Здесь должна быть реализация метода сканирования и возвращения токена
        pass

class Parser:
    def parse(self, scanner, builder):
        # Здесь должна быть реализация метода разбора
        pass

class ProgramNodeBuilder:
    def __init__(self):
        self._node = None

    def new_variable(self, variable_name):
        # Здесь должна быть реализация создания узла переменной
        pass

    def new_assignment(self, variable, expression):
        # Здесь должна быть реализация создания узла присваивания
        pass

    def new_return_statement(self, value):
        # Здесь должна быть реализация создания узла оператора return
        pass

    def new_condition(self, condition, true_part, false_part):
        # Здесь должна быть реализация создания узла условия
        pass

    def get_root_node(self):
        return self._node

class ProgramNode:
    def __init__(self):
        pass

    def get_source_position(self):
        # Здесь должна быть реализация получения позиции источника
        pass

    def add(self, child_node):
        # Здесь должна быть реализация добавления дочернего узла
        pass

    def remove(self, child_node):
        # Здесь должна быть реализация удаления дочернего узла
        pass

    def traverse(self, code_generator):
        # Здесь должна быть реализация обхода узла программы
        pass

class CodeGenerator:
    def __init__(self, output_stream):
        self._output = output_stream

    def visit_statement(self, statement_node):
        # Здесь должна быть реализация посещения узла оператора
        pass

    def visit_expression(self, expression_node):
        # Здесь должна быть реализация посещения узла выражения
        pass

def expression_node_traverse(code_generator):
    code_generator.visit(expression_node)
    for child in expression_node.children:
        child.traverse(code_generator)

class Compiler:
    def compile(self, input_stream, output_stream):
        scanner = Scanner(input_stream)
        builder = ProgramNodeBuilder()
        parser = Parser()
        parser.parse(scanner, builder)
        generator = CodeGenerator(output_stream)
        parse_tree = builder.get_root_node()
        parse_tree.traverse(generator)
