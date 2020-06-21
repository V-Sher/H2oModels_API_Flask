#!/usr/bin/env python3
# -*- coding: utf-8 -*-
"""
Created on Sat Jun 20 15:13:10 2020

@author: vsher
"""

from flask import Flask
from flask_restful import Resource, Api, reqparse
app = Flask(__name__)
api = Api(app)
# argument parsing
parser = reqparse.RequestParser()
parser.add_argument('num1')
parser.add_argument('num2')
class HelloWorld(Resource):
    def get(self):
        return {'hello': 'world'}
class PrintSquare(Resource):
    def get(self):
        # use parser and find the user's input
        args = parser.parse_args()
        
        user_query = float(args['num1'])
        return {'ans': user_query * user_query}
class PrintSum(Resource):
    def get(self):
        # use parser and find the user's inputs
        args = parser.parse_args()
        num1 = float(args['num1'])
        num2 = float(args['num2'])
        return {'ans': num1 + num2}
api.add_resource(HelloWorld, '/hello')
api.add_resource(PrintSquare, '/sq')
api.add_resource(PrintSum, '/sum')
if __name__ == '__main__':
    app.run(debug=True, port = 12345)
